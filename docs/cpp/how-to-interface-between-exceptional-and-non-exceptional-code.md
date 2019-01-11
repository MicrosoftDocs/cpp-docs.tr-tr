---
title: 'Nasıl yapılır: Olağanüstü ve özel durumlu olmayan kod arasında arabirim'
ms.custom: how-to
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: fd5bb4af-5665-46a1-a321-614b48d4061e
ms.openlocfilehash: e8ff92f965f48faa7954ae0364ec7877428e519c
ms.sourcegitcommit: a1fad0a266b20b313364a74b16c9ac45d089b1e9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/11/2019
ms.locfileid: "54220637"
---
# <a name="how-to-interface-between-exceptional-and-non-exceptional-code"></a>Nasıl yapılır: Olağanüstü ve özel durumlu olmayan kod arasında arabirim

Bu makalede, bir C++ modülünde tutarlı özel durum işleme gerçekleştirme ve ayrıca bu özel durumların özel durum sınırlarındaki hata kodlarına/kodlarından çevirmek nasıl açıklar.

Bir C++ modülünün bazen gerekir (durumsuz kod) özel durumlar kullanmayan kod arabirimi. Böyle bir arabirim olarak bilinen bir *özel durum sınırı*. Örneğin, Win32 işlevini çağırmak isteyebilirsiniz `CreateFile` C++ programınızda. `CreateFile` özel durumlar oluşturmaz; Bunun yerine tarafından alınabilen hata kodlarını ayarlar `GetLastError` işlevi. C++ programınız Önemsiz ise, ardından bunu, büyük olasılıkla tutarlı bir özel durum tabanlı hata işleme ilkesi tercih edebilirsiniz. Ve büyük olasılıkla özel durumları çünkü yalnızca özel durumlu olmayan kod ile arabirim ve özel durum tabanlı ve özel durum tabanlı olmayan tabansız hata ilkelerini C++ modülünüzde karıştırmak diğerinden istediğiniz bırakmaya karar istemiyorum.

## <a name="calling-non-exceptional-functions-from-c"></a>C++'tan olmayan durum fonksiyonlarını çağırma

C++'dan olağanüstü olmayan bir işlev çağırdığınızda, bu işlev hatalar varsa algılayan ve muhtemelen bir istisna atan bir C++ işlev içinde sarmalamak olur. Böyle bir sarmalayıcı işlevi tasarlarken, öncelikle sağlamak için özel durum garantisi türüne karar verin: fırlatmasız, güçlü veya temel. İkinci olarak, bir özel durum oluşturulursa tüm kaynakların, örneğin dosya tanıtıcılarının doğru yayımlanır böylece işlev tasarlayın. Genellikle, bu kaynaklara sahip olmak için akıllı işaretçiler veya benzer kaynak yöneticileri kullanmanız anlamına gelir. Tasarım konuları hakkında daha fazla bilgi için bkz. [nasıl yapılır: Özel durum güvenliği tasarımı](../cpp/how-to-design-for-exception-safety.md).

### <a name="example"></a>Örnek

Aşağıdaki örnek, Win32 kullanan C++ işlevlerini gösterir. `CreateFile` ve `ReadFile` işlevleri dahili olarak açmak ve iki dosya okuma için.  `File` Sınıfı, kaynak alımı başlatma (RAII) sarmalayıcı dosya tanıtıcıları için olan. Oluşturucusuna bir "dosya bulunamadı" koşulu algılar ve C++ modülü çağrı yığınına hata yaymak için bir özel durum oluşturur (Bu örnekte, `main()` işlevi). Sonra bir özel durum oluşturulursa bir `File` nesnesi tamamen oluşturulduktan, yıkıcı otomatik olarak çağırır `CloseHandle` dosya tanıtıcısını bırakmak için. (İsterseniz, Etkin Şablon kitaplığı (ATL) kullanabileceğiniz `CHandle` sınıfı, aynı amaçla veya bir `unique_ptr` özel bir siliciyle birlikte.) Win32 ve CRT API çağıran işlevler hataları algılar ve ardından yerel olarak tanımlanan kullanan C++ özel durumlarını throw `ThrowLastErrorIf` sırayla kullanan işlevi, `Win32Exception` sınıfından türetilen `runtime_error` sınıfı. Bu örnekteki tüm işlevler güçlü özel durum garantisi sağlar; Bu işlevlerden herhangi bir noktada bir özel durum oluşturulursa, kaynak sızmaz ve program durumu değiştirilmez.

```cpp
// compile with: /EHsc
#include <Windows.h>
#include <stdlib.h>
#include <vector>
#include <iostream>
#include <string>
#include <limits>
#include <stdexcept>

using namespace std;

string FormatErrorMessage(DWORD error, const string& msg)
{
    static const int BUFFERLENGTH = 1024;
    vector<char> buf(BUFFERLENGTH);
    FormatMessageA(FORMAT_MESSAGE_FROM_SYSTEM, 0, error, 0, buf.data(),
        BUFFERLENGTH - 1, 0);
    return string(buf.data()) + "   ("  + msg  + ")";
}

class Win32Exception : public runtime_error
{
private:
    DWORD m_error;
public:
    Win32Exception(DWORD error, const string& msg)
        : runtime_error(FormatErrorMessage(error, msg)), m_error(error) { }

    DWORD GetErrorCode() const { return m_error; }
};

void ThrowLastErrorIf(bool expression, const string& msg)
{
    if (expression) {
        throw Win32Exception(GetLastError(), msg);
    }
}

class File
{
private:
    HANDLE m_handle;

    // Declared but not defined, to avoid double closing.
    File& operator=(const File&);
    File(const File&);
public:
    explicit File(const string& filename)
    {
        m_handle = CreateFileA(filename.c_str(), GENERIC_READ, FILE_SHARE_READ,
            nullptr, OPEN_EXISTING, FILE_ATTRIBUTE_READONLY, nullptr);
        ThrowLastErrorIf(m_handle == INVALID_HANDLE_VALUE,
            "CreateFile call failed on file named " + filename);
    }

    ~File() { CloseHandle(m_handle); }

    HANDLE GetHandle() { return m_handle; }
};

size_t GetFileSizeSafe(const string& filename)
{
    File fobj(filename);
    LARGE_INTEGER filesize;

    BOOL result = GetFileSizeEx(fobj.GetHandle(), &filesize);
    ThrowLastErrorIf(result == FALSE, "GetFileSizeEx failed: " + filename);

    if (filesize.QuadPart < (numeric_limits<size_t>::max)()) {
        return filesize.QuadPart;
    } else {
        throw;
    }
}

vector<char> ReadFileVector(const string& filename)
{
    File fobj(filename);
    size_t filesize = GetFileSizeSafe(filename);
    DWORD bytesRead = 0;

    vector<char> readbuffer(filesize);

    BOOL result = ReadFile(fobj.GetHandle(), readbuffer.data(), readbuffer.size(),
        &bytesRead, nullptr);
    ThrowLastErrorIf(result == FALSE, "ReadFile failed: " + filename);

    cout << filename << " file size: " << filesize << ", bytesRead: "
        << bytesRead << endl;

    return readbuffer;
}

bool IsFileDiff(const string& filename1, const string& filename2)
{
    return ReadFileVector(filename1) != ReadFileVector(filename2);
}

#include <iomanip>

int main ( int argc, char* argv[] )
{
    string filename1("file1.txt");
    string filename2("file2.txt");

    try
    {
        if(argc > 2) {
            filename1 = argv[1];
            filename2 = argv[2];
        }

        cout << "Using file names " << filename1 << " and " << filename2 << endl;

        if (IsFileDiff(filename1, filename2)) {
            cout << "+++ Files are different." << endl;
        } else {
            cout<< "=== Files match." << endl;
        }
    }
    catch(const Win32Exception& e)
    {
        ios state(nullptr);
        state.copyfmt(cout);
        cout << e.what() << endl;
        cout << "Error code: 0x" << hex << uppercase << setw(8) << setfill('0')
            << e.GetErrorCode() << endl;
        cout.copyfmt(state); // restore previous formatting
    }
}
```

## <a name="calling-exceptional-code-from-non-exceptional-code"></a>Özel durumlu olmayan kod kodundan olağanüstü durum kodunu çağırma

"Dış C" C programları tarafından çağrılabilir olarak bildirilen C++ işlevler. C++ COM sunucuları herhangi bir dizi farklı dillerde yazılan kod tarafından tüketilebilir. Genel özel durum duyarlı işlevleri özel durumlu olmayan kod tarafından çağrılmak üzere uygularken, C++ işlevi özel durumların tekrar çağırana yayılmasına izin vermemesi gerekir. Bu nedenle, C++ işlevi, işlemek ve uygunsa, özel durumu çağıranın anladığı bir hata koduna dönüştürmek bildiği her özel durum özellikle yakalamalıdır. Tüm potansiyel özel durumlar bilinmiyorsa, C++ işlevi olmalıdır bir `catch(...)` son işleyici olarak blok. Programınız bilinmeyen bir durumda olabilir. böyle bir durumda, en iyisi arayana önemli bir hata raporu olmasıdır.

Aşağıdaki örnek oluşturulabilecek tüm özel bir Win32Exception veya türetilmiş bir özel durum türü olduğunu varsayan bir işlev gösterir `std::exception`. İşlevi, bu tür herhangi bir özel durumu yakalar ve hata bilgisini çağırana bir Win32 hata kodu olarak yayar.

```cpp
BOOL DiffFiles2(const string& file1, const string& file2)
{
    try
    {
        File f1(file1);
        File f2(file2);
        if (IsTextFileDiff(f1, f2))
        {
            SetLastError(MY_APPLICATION_ERROR_FILE_MISMATCH);
            return FALSE;
        }
        return TRUE;
    }
    catch(Win32Exception& e)
    {
        SetLastError(e.GetErrorCode());
    }

    catch(std::exception& e)
    {
        SetLastError(MY_APPLICATION_GENERAL_ERROR);
    }
    return FALSE;
}
```

Özel durumlardan hata kodlarına dönüştürdüğünüzde, hata kodlarının genellikle bir özel durumun depolayabileceği bilgi zenginliği içermeyen bir olası sorun olduğunu. Bunu ele almak için sağlayabilirsiniz bir **catch** blok harekete geçirilebilirse ve bir hata koduna dönüştürülmeden önce özel durumun ayrıntılarını kaydetmek için günlük işlemi her özel durum türü. Birden fazla işlevin hepsi aynı kümesi kullanıyorsanız bu yaklaşım çok fazla kod tekrarı oluşturabilir **catch** engeller. Kod tekrarından kaçınmanın en iyi yolu, söz konusu bloklar uygulayan bir özel bir yardımcı programda yeniden düzenlemektir tarafından olan **deneyin** ve **catch** engeller ve içindeçağrılanişlevnesnesinikabul**deneyin** blok. Her ortak işlev kodunda, kodu lambda ifadesiyle yardımcı program işlevine geçirin.

```cpp
template<typename Func>
bool Win32ExceptionBoundary(Func&& f)
{
    try
    {
        return f();
    }
    catch(Win32Exception& e)
    {
        SetLastError(e.GetErrorCode());
    }
    catch(const std::exception& e)
    {
        SetLastError(MY_APPLICATION_GENERAL_ERROR);
    }
    return false;
}
```

Aşağıdaki örnek işlev nesnesini tanımlayan lambda ifadesinin nasıl yazılacağını gösterir. Bir functor, lambda ifadesi kullanılarak "satır içi" olduğunda, genellikle bu yazılmış bir adlandırılmış işlev nesnesi olarak olmasına kıyasla okuması daha kolay olur.

```cpp
bool DiffFiles3(const string& file1, const string& file2)
{
    return Win32ExceptionBoundary([&]() -> bool
    {
        File f1(file1);
        File f2(file2);
        if (IsTextFileDiff(f1, f2))
        {
            SetLastError(MY_APPLICATION_ERROR_FILE_MISMATCH);
            return false;
        }
        return true;
    });
}
```

Lambda ifadeleri hakkında daha fazla bilgi için bkz. [Lambda ifadeleri](../cpp/lambda-expressions-in-cpp.md).

## <a name="see-also"></a>Ayrıca bkz.

[Hatalar ve Özel Durum İşleme (Modern C++)](../cpp/errors-and-exception-handling-modern-cpp.md)<br/>
[Nasıl yapılır: Özel durum güvenliği tasarımı](../cpp/how-to-design-for-exception-safety.md)<br/>
