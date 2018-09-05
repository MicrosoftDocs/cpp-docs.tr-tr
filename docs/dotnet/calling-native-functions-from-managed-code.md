---
title: Yönetilen koddan yerel işlevleri çağırma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- native functions called from managed code [C++]
- managed code [C++], interoperability
- platform invoke [C++], interoperability
- interoperabiliy [C++], calling native functions from managed code
- calling native functions from managed code
- interop [C++], calling native functions from managed code
ms.assetid: 982cef18-20d9-42b4-8242-a77fa65f2e36
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 3ef47e3aeb8cfb18dd1eb6497c593d8cec26081b
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/04/2018
ms.locfileid: "43678456"
---
# <a name="calling-native-functions-from-managed-code"></a>Yönetilen Koddan Yerel İşlevleri Çağırma
Platform çağırma Hizmetleri veya PInvoke sağlar yönetilen kodun yerel dinamik bağlantı kitaplıklarında (DLL'ler) C stili işlevleri çağırmak için ortak dil çalışma zamanı sağlar. Aynı veri sıralama, çalışma zamanı ile ve "It Just Works" öğesi veya IJW, mekanizma için COM birlikte çalışabilirlik için kullanılır.  
  
 Daha fazla bilgi için bkz.:  
  
-   [C++'ta Açık PInvoke Kullanma (DllImport Özniteliği)](../dotnet/using-explicit-pinvoke-in-cpp-dllimport-attribute.md)  
  
-   [C++ Birlikte Çalışabilirliği Kullanma (Örtük PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md)  
  
 Bu bölümdeki örnekler yalnızca göstermek nasıl `PInvoke` kullanılabilir. `PInvoke` yordam sıralama kodu yazmak yerine bildirimli olarak öznitelikler sıralama bilgilerini sağlamak için özelleştirilmiş veri hazırlama basitleştirebilir.  
  
> [!NOTE]
>  Sıralama kitaplığı, bir en iyi duruma getirilmiş şekilde yerel ve yönetilen ortamlar arasında verileri sıralamak için alternatif bir yol sağlar. Bkz: [Overview of Marshaling c++](../dotnet/overview-of-marshaling-in-cpp.md) sıralama kitaplığı hakkında daha fazla bilgi için. Sıralama Kitaplığı işlevler için değil ve yalnızca veriler için kullanılabilir.  
  
## <a name="pinvoke-and-the-dllimport-attribute"></a>PInvoke ve DllImport özniteliği  
 Aşağıdaki örnek kullanımını gösterir `PInvoke` Visual C++ programında. Yerel işlev Msvcrt.dll'de tanımlanır. DllImport özniteliği bildirimi için kullanılır.  
  
```  
// platform_invocation_services.cpp  
// compile with: /clr  
using namespace System;  
using namespace System::Runtime::InteropServices;  
  
[DllImport("msvcrt", CharSet=CharSet::Ansi)]  
extern "C" int puts(String ^);  
  
int main() {  
   String ^ pStr = "Hello World!";  
   puts(pStr);  
}  
```  
  
 Aşağıdaki örnek önceki örneğe eşdeğerdir, ancak IJW kullanır.  
  
```  
// platform_invocation_services_2.cpp  
// compile with: /clr  
using namespace System;  
using namespace System::Runtime::InteropServices;  
  
#include <stdio.h>  
  
int main() {  
   String ^ pStr = "Hello World!";  
   char* pChars = (char*)Marshal::StringToHGlobalAnsi(pStr).ToPointer();   
   puts(pChars);  
  
   Marshal::FreeHGlobal((IntPtr)pChars);  
}  
```  
  
### <a name="advantages-of-ijw"></a>IJW avantajları  
  
-   Yazmaya gerek yoktur `DLLImport` öznitelik bildirimlerini programın kullandığı yönetilmeyen API'lara için. Yalnızca üst bilgi dosyası ve içeri aktarma kitaplığı ile bağlantı içerir.  
  
-   IJW mekanizması biraz daha hızlıdır (örneğin, IJW saplamalarının açıkça geliştirici tarafından yapıldığı için PIN veya kopya veri öğeleri için gereken denetlemek gerekmez).  
  
-   Performans sorunlarını açıkça gösterir. Bu durumda, bir Unicode dizesini bir ANSI dizesine ve aldığınız çevireceğiniz bir olgu bir katılımcısı bellek ayırmayı ve ayırmayı kaldırma vardır. Bu durumda, IJW kullanarak kodu yazan geliştirici çağırmanın fark `_putws` ve kullanarak `PtrToStringChars` performans için daha iyi olur.  
  
-   Geçirme ve sonra bunu aynı veriyi kullanarak birçok yönetilmeyen API çağırırsanız, hazırlamak ve hazırlanmış kopyayı her seferinde yeniden hazırlamaktan çok daha verimlidir.  
  
### <a name="disadvantages-of-ijw"></a>IJW dezavantajları  
  
-   Hazırlama açıkça değil, kod içinde (Bu, çoğu zaman uygun varsayılanlara sahiptir) öznitelikleri belirtilmesi gerekir.  
  
-   Sıralama kodu uygulama mantığının akışında daha bozucu olduğu satır içi, olan.  
  
-   Açık sıralama API'ları döndürdüğünden `IntPtr` türleri 32-bit mimarilerden 64-bit taşınabilirlik için kullanmanız gerekir fazladan `ToPointer` çağırır.  
  
 C++ tarafından sunulan belirli yöntem daha verimli ve açık yöntem, bazı ek karmaşıklıklar pahasına olur.  
  
 Uygulama ağırlıklı olarak yönetilmeyen veri türleri kullanıyorsa ya da daha fazla yönetilmeyen API .NET Framework API'ları çağırırsa, öneririz IJW özelliğini kullanın. Çoğunlukla yönetilen uygulamada nadiren yönetilmeyen API çağırmak için seçim daha inceliklidir.  
  
## <a name="pinvoke-with-windows-apis"></a>Windows API'ları içeren PInvoke  
 PInvoke Windows işlevleri çağırmak için uygundur.  
  
 Bu örnekte, bir Visual C++ programı Win32 API'ın bir parçası olan MessageBox işleviyle birlikte çalışır.  
  
```  
// platform_invocation_services_4.cpp  
// compile with: /clr /c  
using namespace System;  
using namespace System::Runtime::InteropServices;  
typedef void* HWND;  
[DllImport("user32", CharSet=CharSet::Ansi)]  
extern "C" int MessageBox(HWND hWnd, String ^ pText, String ^ pCaption, unsigned int uType);  
  
int main() {  
   String ^ pText = "Hello World! ";  
   String ^ pCaption = "PInvoke Test";  
   MessageBox(0, pText, pCaption, 0);  
}  
```  
  
 Çıktı, PInvoke testi başlığına sahip ve Hello World metnini içeren bir ileti kutusudur!.  
  
 Sıralama bilgileri DLL'deki işlevleri aramak için PInvoke tarafından da kullanılır. User32.dll öğesinde yok aslında hiçbir MessageBox işlevi, ancak CharSet:: Ansi etkinleştirir Unicode sürümü olan MessageBoxW yerine ANSI sürümü olan MessageBoxA kullanılacak PInvoke =. Genel olarak, bu çevirme yükünü yerel Unicode biçimlerini .NET Framework dize nesnelerinin ANSI attığından yönetilmeyen API'ların Unicode sürümlerini kullanmanızı öneririz.  
  
## <a name="when-not-to-use-pinvoke"></a>Ne zaman PInvoke kullanma  
 PInvoke kullanma, DLL'lerdeki tüm C-stili işlevler için uygun değil. Örneğin, bir ' % s'işlevi MakeSpecial mylib.dll içinde şu şekilde bildirilir var. varsayalım:  
  
 `char * MakeSpecial(char * pszString);`  
  
 Bir Visual C++ uygulamasında PInvoke kullanıyoruz, biz aşağıdakine benzer bir şey yazabiliriz:  
  
 `[DllImport("mylib")]`  
  
 `extern "C" String * MakeSpecial([MarshalAs(UnmanagedType::LPStr)] String ^);`  
  
 Buradaki zorluk MakeSpecial tarafından döndürülen yönetilmeyen dize için belleği silinemiyor ' dir. PInvoke aracılığıyla çağrılan diğer işlevler kullanıcı tarafından serbest bırakılması sahip olmayan bir iç arabellek bir işaretçi döndürür. Bu durumda, IJW özelliğini kullanarak belirgin bir seçimdir.  
  
## <a name="limitations-of-pinvoke"></a>PInvoke sınırlamaları  
 Bir parametre olarak aldığınız yerel bir işlevden işaretçinin aynısını döndüremezsiniz. Yerel bir işlev sıralanmış işaretçiyi için PInvoke tarafından döndürürse, Bellek Bozulması ve özel durumlar oluşması beklenebilir.  
  
```  
__declspec(dllexport)  
char* fstringA(char* param) {  
   return param;  
}  
```  
  
 Aşağıdaki örnek bu sorunu gösterir ve program doğru çıktıyı veriyor gibi görünse de, çıktı serbest bırakılan bellekten gelmektedir.  
  
```  
// platform_invocation_services_5.cpp  
// compile with: /clr /c  
using namespace System;  
using namespace System::Runtime::InteropServices;  
#include <limits.h>  
  
ref struct MyPInvokeWrap {  
public:  
   [ DllImport("user32.dll", EntryPoint = "CharLower", CharSet = CharSet::Ansi) ]  
   static String^ CharLower([In, Out] String ^);  
};  
  
int main() {  
   String ^ strout = "AabCc";  
   Console::WriteLine(strout);  
   strout = MyPInvokeWrap::CharLower(strout);  
   Console::WriteLine(strout);  
}  
```  
  
## <a name="marshaling-arguments"></a>Bağımsız değişkenleri sıralama  
 İle `PInvoke`, sıralamaya gerek yoktur arasında yönetilen ve C++ yerel temel türler aynı forma sahip. Örneğin, herhangi bir sıralama Int32 ve int arasında veya Double ve double arasında gerekli değildir.  
  
 Ancak, aynı forma sahip olmayan türleri sıralamanız gerekir. Bu, char, string ve struct türlerini içerir. Aşağıdaki tabloda, çeşitli türler için sıralayıcı tarafından kullanılan eşlemeleri gösterir:  
  
|wtypes.h|Visual C++|Visual C++/CLR ile|Ortak dil çalışma zamanı|  
|--------------|------------------|-----------------------------|-----------------------------|  
|TANITICI|Geçersiz kılma \*|Geçersiz kılma \*|IntPtr, UIntPtr|  
|BYTE|unsigned char|unsigned char|Bayt|  
|KISA|short|short|Int16|  
|WORD|imzasız short|imzasız short|UInt16|  
|INT|int|int|Int32|  
|UINT|unsigned int|unsigned int|UInt32|  
|UZUN|long|long|Int32|  
|BOOL|long|bool|Boole değeri|  
|DWORD|imzasız long|imzasız long|UInt32|  
|ULONG|imzasız long|imzasız long|UInt32|  
|CHAR|char|char|Char|  
|LPCSTR|Char \*|String ^ [in], StringBuilder ^ [içinde out]|String ^ [in], StringBuilder ^ [içinde out]|  
|LPCSTR|const char \*|String ^|Dize|  
|LPWSTR|wchar_t \*|String ^ [in], StringBuilder ^ [içinde out]|String ^ [in], StringBuilder ^ [içinde out]|  
|LPCWSTR|wchar_t const \*|String ^|Dize|  
|KAYAN NOKTA|float|float|Tek|  
|ÇİFT|çift|çift|Çift|  
  
 Sıralayıcı otomatik olarak adresini yönetilmeyen bir işleve geçirilirse, çalışma zamanı yığınına ayrılmış belleği sabitler. Sabitleme, çöp toplayıcısının ayrılan bellek bloğunu sıkıştırma sırasında taşımasını engeller.  
  
 Bu konunun önceki bölümlerinde gösterilen örnekte, DllImport öğesinin CharSet parametresi yönetilen dizelerini belirtir. sıralanmalıdır; Bu durumda, bunlar yerel taraf için ANSI dizelerine sıralanmalıdır.  
  
 MarshalAs özniteliğini kullanılarak bir yerel işlevin tek tek bağımsız değişkenleri için sıralama bilgilerini belirtebilirsiniz. Bir dize için birkaç seçenek vardır \* bağımsız değişken: BStr, ANSIBStr, TBStr, LPStr, LPWStr ve LPTStr. Varsayılan, LPStr'dir.  
  
 Bu örnekte, dize bir çift baytlık Unicode karakter dizesi, LPWStr olarak sıralanır. Çıktı Hello World ilk harfidir! sıralanmış dizenin ikinci baytı NULL'dur ve puts bunu dize sonu işareti olarak yorumlar.  
  
```  
// platform_invocation_services_3.cpp  
// compile with: /clr  
using namespace System;  
using namespace System::Runtime::InteropServices;  
  
[DllImport("msvcrt", EntryPoint="puts")]  
extern "C" int puts([MarshalAs(UnmanagedType::LPWStr)] String ^);  
  
int main() {  
   String ^ pStr = "Hello World!";  
   puts(pStr);  
}  
```  
  
 MarshalAs özniteliği System::Runtime:: InteropServices ad alanındadır. Öznitelik, diziler gibi diğer veri türleri ile kullanılabilir.  
  
 Konunun önceki kısımlarında belirtildiği gibi sıralama kitaplığı, yerel ve yönetilen ortamlar arasında veri hazırlama yeni ve en iyi duruma getirilmiş bir yöntem sağlar. Daha fazla bilgi için [Overview of Marshaling c++](../dotnet/overview-of-marshaling-in-cpp.md).  
  
## <a name="performance-considerations"></a>Başarım Değerlendirmeleri  
 PInvoke 10 ila 30 yüküne sahiptir x86 çağrı başına yönergeleri. Bu sabit maliyete ek olarak, sıralama ek yük oluşturur. Yönetilen ve yönetilmeyen kod içinde aynı gösterimi içeren Taşınabilir türler arasında hiçbir sıralama maliyeti yoktur. Örneğin, int ve Int32 arasında dönüştürme maliyeti yoktur.  
  
 Daha iyi performans için çağrı başına daha az veri hazırlama daha fazla çağrı yerine, mümkün olduğunca kadar veri hazırlama daha az PInvoke çağrısına sahip olun.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yerel ve.NET Birlikte Çalışabilirliği](../dotnet/native-and-dotnet-interoperability.md)