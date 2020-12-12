---
description: 'Hakkında daha fazla bilgi edinin: nasıl yapılır: olağanüstü ve olağanüstü olmayan kod arasında arabirim'
title: 'Nasıl yapılır: olağanüstü ve olağanüstü olmayan kod arasında arabirim'
ms.custom: how-to
ms.date: 11/19/2019
ms.topic: conceptual
ms.assetid: fd5bb4af-5665-46a1-a321-614b48d4061e
ms.openlocfilehash: 34a0966d496e5e22099de051a74f3458d1cc05d0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97114032"
---
# <a name="how-to-interface-between-exceptional-and-non-exceptional-code"></a>Nasıl yapılır: olağanüstü ve olağanüstü olmayan kod arasında arabirim

Bu makalede, bir C++ modülünde tutarlı özel durum işlemenin nasıl uygulanacağı ve ayrıca özel durum sınırlarındaki hata kodlarından ve bu özel durumların nasıl çevrilebileceğiniz açıklanır.

Bazen bir C++ modülünün özel durumlar kullanmayan kodla arabirimi olması (olağanüstü olmayan kod). Bu tür bir arabirim, *özel durum sınırı* olarak bilinir. Örneğin, C++ programınızda Win32 işlevini çağırmak isteyebilirsiniz `CreateFile` . `CreateFile` özel durumlar oluşturmaz; Bunun yerine, işlevi tarafından alınabilecek hata kodlarını ayarlar `GetLastError` . C++ programınız önemsiz değilse, büyük olasılıkla tutarlı bir özel durum tabanlı hata işleme ilkesine sahip olmayı tercih edersiniz. Büyük olasılıkla, özel durum olmayan kod ile arabirim oluşturmanız ve bu nedenle, C++ modülünüzün özel durum tabanlı ve özel durum tabanlı hata ilkelerini karıştırmak istemezsiniz.

## <a name="calling-non-exceptional-functions-from-c"></a>C++ ' dan olağanüstü olmayan işlevler çağırma

C++ ' dan olağanüstü olmayan bir işlevi çağırdığınızda, bu işlevi herhangi bir hata algılayan ve büyük olasılıkla özel durum oluşturan bir C++ işlevinde sarmanız gerekir. Böyle bir sarmalayıcı işlevi tasarlarken, ilk olarak hangi tür özel durum garantisi sağlayacağınıza karar verin: throw, Strong veya Basic. İkinci olarak, bir özel durum oluşturulursa, örneğin dosya tutamaçları gibi tüm kaynakların doğru şekilde serbest bırakılması için işlevi tasarlayın. Genellikle bu, kaynaklara sahip olmak için akıllı işaretçiler veya benzer kaynak yöneticileri kullandığınız anlamına gelir. Tasarım konuları hakkında daha fazla bilgi için bkz. [nasıl yapılır: özel durum güvenliği tasarımı](how-to-design-for-exception-safety.md).

### <a name="example"></a>Örnek

Aşağıdaki örnek, `CreateFile` `ReadFile` iki dosyayı açmak ve okumak için Win32 ve Işlevleri kullanan C++ işlevlerini gösterir.  `File`Sınıfı, dosya tutamaçları için bir kaynak alımı başlatma (rampasıdır) sarmalayıcısı. Oluşturucusu bir "dosya bulunamadı" koşulu algılar ve hatayı, C++ modülünün çağrı yığınını (Bu örnekte, işlevi) yaymak için bir özel durum oluşturur `main()` . Bir nesne tam olarak oluşturulduktan sonra bir özel durum oluşturulursa `File` , yıkıcı otomatik olarak `CloseHandle` dosya tanıtıcısını serbest bırakma yöntemini çağırır. (İsterseniz, etkin şablon kitaplığı (ATL) `CHandle` sınıfını aynı amaçla veya `unique_ptr` özel bir silici ile birlikte kullanabilirsiniz.) Win32 ve CRT API 'Leri çağıran işlevler hataları algılar ve ardından yerel olarak tanımlanmış işlevini kullanarak C++ özel durumlarını oluşturur `ThrowLastErrorIf` , bu, sınıfından `Win32Exception` türetilen sınıfını kullanır `runtime_error` . Bu örnekteki tüm işlevler güçlü bir özel durum garantisi sağlar; Bu işlevlerin herhangi bir noktasında bir özel durum oluşturulursa, hiçbir kaynak sızdırılmaz ve program durumu değiştirilmez.

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

## <a name="calling-exceptional-code-from-non-exceptional-code"></a>Olağanüstü olmayan koddan olağanüstü kodu çağırma

"Extern C" olarak belirtilen C++ işlevleri, C programları tarafından çağrılabilir. C++ COM sunucuları birçok farklı dilde yazılan kodla tüketilebilir. C++ ' da özel durum algılayan işlevleri olağanüstü olmayan kod tarafından çağrılacak şekilde uyguladığınızda, C++ işlevi herhangi bir özel durumun çağırana geri yaymaya izin vermiyor olmalıdır. Bu nedenle, C++ işlevi, nasıl işleneceğini bildiği her özel durumu özel olarak yakalamalı ve uygunsa, özel durumu çağıranın anladığı bir hata koduna dönüştürmelidir. Olası tüm özel durumlar bilinmediği sürece, C++ işlevinin `catch(...)` son işleyici olarak bir bloğu olmalıdır. Böyle bir durumda, programınız bilinmeyen bir durumda olabileceğinden, çağırana önemli bir hata bildirmek en iyisidir.

Aşağıdaki örnek, oluşturulan herhangi bir özel durumun bir Win32Exception ya da öğesinden türetilmiş bir özel durum türü olduğunu varsayan bir işlevi gösterir `std::exception` . İşlevi bu türlerin herhangi bir özel durumunu yakalar ve hata bilgilerini çağırana bir Win32 hata kodu olarak yayar.

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

Özel durumlardan hata kodlarına dönüştürdüğünüzde, olası bir sorun, hata kodlarının genellikle bir özel durumun depolayabileceği bilgilerin zenginliği içermez. Bunu çözmek için, oluşturulabilecek her bir özel **`catch`** durum türü için bir blok sağlayabilir ve bir hata koduna dönüştürülmeden önce özel durumun ayrıntılarını kaydetmek için günlüğe kaydetmeyi gerçekleştirebilirsiniz. Bu yaklaşım, birden fazla işlev aynı blok kümesini kullanıyorsa, çok sayıda kod yinelemesi oluşturabilir **`catch`** . Kod tekrarından kaçınmanın iyi bir yolu, bu blokları **`try`** ve **`catch`** bloklarını uygulayan ve bloğunda çağrılan bir işlev nesnesini kabul eden bir özel yardımcı program işlevine yeniden düzenlemedir **`try`** . Her genel işlevde, kodu bir lambda ifadesi olarak yardımcı program işlevine geçirin.

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

Aşağıdaki örnek, functor tanımlayan lambda ifadesinin nasıl yazılacağını gösterir. Bir functor "satır içi" olarak tanımlandığında, bir lambda ifadesi kullanılarak okunması genellikle daha kolaydır, bu, adlandırılmış bir işlev nesnesi olarak yazılmışsa daha kolay olur.

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

Lambda ifadeleri hakkında daha fazla bilgi için bkz. [lambda ifadeleri](lambda-expressions-in-cpp.md).

## <a name="see-also"></a>Ayrıca bkz.

[Özel durumlar ve hata işleme için modern C++ en iyi uygulamaları](errors-and-exception-handling-modern-cpp.md)<br/>
[Nasıl yapılır: özel durum güvenliği için tasarım](how-to-design-for-exception-safety.md)<br/>
