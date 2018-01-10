---
title: "Nasıl yapılır: özel durumlu ve özel durumlu olmayan kod arasındaki arabirim | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: fd5bb4af-5665-46a1-a321-614b48d4061e
caps.latest.revision: "14"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 59838fa1797fc87561b081d40143693dea385668
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-interface-between-exceptional-and-non-exceptional-code"></a>Nasıl yapılır: Özel Durumlu Kod ve Özel Durumlu Olmayan Kod Arasındaki Arabirim
Bu makalede nasıl tutarlı özel durum işlemeyi C++ modülünde uygulanacağını ve bu özel durumlar için ve özel durum sınırlarında hata kodlarından Çevir nasıl açıklanmaktadır.  
  
 C++ modülü bazen gerekir özel durumları (özel durumlu olmayan kod) kullanmayan kodu arabirimi. Böyle bir arabirim olarak bilinen bir *özel durum sınır*. Örneğin, Win32 işlevi çağırmak isteyebilir `CreateFile` C++ programı. `CreateFile`özel durumlar oluşturma değil; Bunun yerine tarafından alınan hata kodları ayarlar `GetLastError` işlevi. C++ programı Önemsiz olmayan ise, ardından içinde büyük olasılıkla tutarlı bir özel durum tabanlı hata işleme ilkesi olması tercih edilir. Ve büyük olasılıkla yalnızca özel durumlu olmayan kod ile arabirim ve, C++ modülünde hata özel durum tabanlı ve özel durum tabanlı ilkeleri karıştırmak istediğiniz özel durumlar bırakmasını istemiyorum.  
  
## <a name="calling-non-exceptional-functions-from-c"></a>C++ içinden özel durumlu olmayan işlevleri çağırma  
 C++ içinden özel durumlu olmayan bir işlev çağırdığınızda, bu işlev hataları algılar ve büyük olasılıkla bir özel durum oluşturur C++ işlevinde sarmalamak olur. Bu tür bir sarmalayıcı işlevi tasarlarken, özel durum garantisi sağlamak için hangi tür ilk karar verin: Hayır throw, güçlü veya temel. İkinci olarak, bir özel durum, tüm kaynaklar, örneğin, dosya tanıtıcıları doğru serbest şekilde işlevi tasarlayın. Genellikle, bu kaynakları sahibi Akıllı işaretçiler veya benzer kaynak yöneticileri kullanmak anlamına gelir. Tasarım konuları hakkında daha fazla bilgi için bkz: [nasıl yapılır: özel durum güvenliği tasarımı](../cpp/how-to-design-for-exception-safety.md).  
  
### <a name="example"></a>Örnek  
 Aşağıdaki örnek, Win32 kullanmak için C++ işlevlerini gösterir `CreateFile` ve `ReadFile` işlevleri dahili olarak açabilir ve iki dosyaları okuyabilir.  `File` Sınıfı, bir kaynak edinme olan dosya işleyici için başlatma (RAII) sarmalayıcı. Kurucusu "dosya bulunamadı" koşul algılar ve C++ modülü çağrı yığınını hata yaymak için bir özel durum oluşturur (Bu örnekte, `main()` işlevi). Sonra bir özel durum, bir `File` nesnesi tam olarak oluşturulan, otomatik olarak yıkıcı çağrıları `CloseHandle` dosya tanıtıcısı serbest bırakmak için. (Tercih ederseniz, Etkin Şablon kitaplığı (ATL) kullanabilirsiniz `CHandle` aynı bu amaç için sınıf veya `unique_ptr` özel bir Silici birlikte.) Win32 ve CRT API'leri çağırmak işlevler hataları algılar ve yerel olarak tanımlanan kullanarak C++ özel durumlarını throw `ThrowLastErrorIf` sırayla kullanan işlevi `Win32Exception` türetilmiş sınıf `runtime_error` sınıfı. Bu örnek uygulamasında tüm işlevleri güçlü özel durum garantisi sağlar; Bu işlevler herhangi bir noktada bir özel durum, kaynak sızmasını ve hiçbir program durumu değiştirilebilir.  
  
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
            cout << "*** Files are different." << endl;  
        } else {  
            cout<< "*** Files match." << endl;  
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
  
## <a name="calling-exceptional-code-from-non-exceptional-code"></a>Özel durumlu olmayan kod olağanüstü kodu çağırma  
 "Extern C" C programlar tarafından çağrılabilir olarak bildirilen C++ işlevlerini. C++ COM sunucusu herhangi bir dizi farklı dillerde yazılmış kod tarafından kullanılabilecek. C++ özel durumlu olmayan kod tarafından çağrılacak ortak özel durumu algılayan işlevleri uyguladığınızda, C++ işlevi geri çağırana yaymak özel durumlar izin vermemelidir. Bu nedenle, C++ işlevi işlemek ve uygunsa, özel durum çağıran özelliğini algılayan bir hata kodu dönüştürmek nasıl bilir her özel durum özellikle catch gerekir. Tüm olası özel durumlar biliniyorsa, C++ işlevi olmalıdır bir `catch(...)` bloğu son işleyici olarak. Programınızı bilinmeyen bir durumda olabileceğinden böyle bir durumda çağırana önemli bir hata raporu en iyisidir.  
  
 Aşağıdaki örnek, durum herhangi bir özel durum bir Win32Exception veya türetilmiş bir özel durum türü olduğunu varsayar. bir işlev gösterir `std::exception`. İşlevi bu tür özel durumları yakalar ve hata bilgilerini çağırana Win32 hata kodu olarak yayar.  
  
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
  
 Hata kodları için özel durumları dönüştürme olası bir sorunu hata kodları genellikle bir özel durum depolayabilir bilgi zenginliğinin içermeyen olur. Bu sorunu çözmek için sağlayabilirsiniz bir `catch` durum ve bir hata kodu dönüştürülmeden önce özel durum ayrıntıları kaydetmek için günlüğe kaydetme gerçekleştirebilirsiniz her bir özel durum türü için blok. Birden çok işlevler tümünü aynı kümesini kullanıyorsanız bu yaklaşım çok fazla kod yineleme oluşturabilirsiniz `catch` engeller. Uygulayan bir özel yardımcı programı işlevdeki bu blokları yeniden düzenleme kod yineleme önlemek için en iyi yolu olan `try` ve `catch` engeller ve içinde çağrılan işlev nesnesi kabul eden `try` bloğu. Her ortak işlevinde kodu için yardımcı program işlevi bir lambda ifadesi geçirin.  
  
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
  
 Aşağıdaki örnekte nasıl functor tanımlayan lambda ifadesi yazılacağını gösterir. Lambda ifadesi kullanarak bir functor "satır içi olarak tanımlanan" olduğunda, genellikle yazılmış, adlandırılmış işlev nesnesi durumdakinden daha okumak kolaydır.  
  
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
  
 Lambda ifadeleri hakkında daha fazla bilgi için bkz: [Lambda ifadeleri](../cpp/lambda-expressions-in-cpp.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hatalar ve özel durum işleme](../cpp/errors-and-exception-handling-modern-cpp.md)   
 [Nasıl yapılır: Özel Durum Güvenliği Tasarımı](../cpp/how-to-design-for-exception-safety.md)