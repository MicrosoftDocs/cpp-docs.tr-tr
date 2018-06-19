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
ms.openlocfilehash: c0d7e69c95790122f44dc59d06f2843afbddfb2c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33112049"
---
# <a name="calling-native-functions-from-managed-code"></a>Yönetilen Koddan Yerel İşlevleri Çağırma
Ortak dil çalışma zamanı Platform Başlatma Hizmetleri ya da yerel dinamik bağlantı kitaplıkları (dll) C stili işlevleri çağırmak için kodu yönetilen tanır PInvoke sağlar. Aynı veri hazırlama "Sadece çalışır" ya da IJW, mekanizması için çalışma zamanı ile COM birlikte çalışabilirliği için kullanılır.  
  
 Daha fazla bilgi için bkz.:  
  
-   [C++'ta Açık PInvoke Kullanma (DllImport Özniteliği)](../dotnet/using-explicit-pinvoke-in-cpp-dllimport-attribute.md)  
  
-   [C++ Birlikte Çalışabilirliği Kullanma (Örtük PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md)  
  
-   [Yakından Platform çağırma](http://msdn.microsoft.com/en-us/ba9dd55b-2eaa-45cd-8afd-75cb8d64d243)  
  
 Bu bölümdeki örnekler yalnızca göstermek nasıl `PInvoke` kullanılabilir. `PInvoke` yordam sıralama kodu yazmak yerine bildirimli olarak öznitelikler hazırlama bilgi sağlamak için özelleştirilmiş verileri hazırlama basitleştirebilirsiniz.  
  
> [!NOTE]
>  Hazırlama kitaplığını en iyi duruma getirilmiş bir yöntem yerel ve Yönetilen ortamlarda arasında verileri hazırlamak için alternatif bir yol sağlar. Bkz: [, genel bakış hazırlama c++](../dotnet/overview-of-marshaling-in-cpp.md) hazırlama kitaplığını hakkında daha fazla bilgi. Hazırlama kitaplığını, yalnızca veri ve işlevleri için kullanılabilir.  
  
## <a name="pinvoke-and-the-dllimport-attribute"></a>PInvoke ve DllImport özniteliği  
 Aşağıdaki örnek kullanımı gösterilmiştir `PInvoke` Visual C++ programı. Yerel işlev Msvcrt.dll'de tanımlanır. DllImport özniteliği yerleştirmelerin bildirimi için kullanılır.  
  
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
  
 Aşağıdaki örnek, önceki örneğe eşdeğerdir ancak IJW kullanır.  
  
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
  
-   Yazmaya gerek yoktur `DLLImport` öznitelik bildirimlerini programın kullandığı yönetilmeyen API'ler için. Yalnızca içeri aktarma kitaplığı ile bağlantı ve üstbilgi dosyası içerir.  
  
-   IJW mekanizması biraz daha hızlıdır (örneğin, IJW saplamalar, geliştirici tarafından açıkça yapıldığından PIN veya kopya veri öğeleri gerek olup olmadığını denetlemek gerekmez).  
  
-   Performans sorunlarını açıkça gösterir. Bu durumda, bir ANSI dize ve sizin için bir Unicode dizeden çevirme olgu Katılımcısı bellek ayırma ve kaldırma vardır. Bu durumda, IJW kullanarak kodu yazan bir geliştirici çağırmanın fark `_putws` ve kullanarak `PtrToStringChars` performans için daha iyi olur.  
  
-   Bir kez ve geçirerek hazırlama aynı verileri kullanarak çok yönetilmeyen API çağırırsanız, sıralanmış kopyalama her zaman yeniden sıralama'den çok daha etkilidir.  
  
### <a name="disadvantages-of-ijw"></a>IJW dezavantajları  
  
-   Hazırlama açıkça yerine kodda (genellikle uygun olan) öznitelikleri tarafından belirtilmesi gerekir.  
  
-   Sıralama satır içi, uygulama mantığını akışında daha bozucu olduğu kodudur.  
  
-   Açık sıralama API'ları geri `IntPtr` 32-bit 64-bit taşınabilirlik türlerinde, kullanmalısınız fazladan `ToPointer` çağrıları.  
  
 C++ tarafından sunulan belirli yöntem daha verimli ve açık yöntem, bazı ek karmaşıklıklar pahasına olur.  
  
 Esas olarak yönetilmeyen veri türleri uygulamanın kullandığı ya da .NET Framework API'den fazla yönetilmeyen API çağrıları, öneririz IJW özelliğini kullanın. Çoğunlukla yönetilen bir uygulamada bir arada sırada yönetilmeyen API çağrısı için daha hafif seçimdir.  
  
## <a name="pinvoke-with-windows-apis"></a>Windows API'leri ile PInvoke  
 PInvoke, Windows'daki işlevleri çağırmak için uygundur.  
  
 Bu örnekte, bir Visual C++ programı Win32 API parçası olan MessageBox işleviyle birlikte çalışır.  
  
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
  
 Çıktı, PInvoke testi başlığına sahip ve Hello World metnini içeren bir ileti kutusu şeklindedir!.  
  
 Sıralama bilgileri DLL'deki işlevleri aramak için PInvoke tarafından da kullanılır. User32.dll öğesinde yok aslında hiçbir MessageBox işlevi, ancak CharSet =:: Ansi etkinleştirir PInvoke Unicode sürümü MessageBoxW yerine MessageBoxA ANSI sürümü kullanın. Genel olarak, bu çevirme yükünü yerel Unicode biçimini .NET Framework dize nesnelerinin ANSI attığından yönetilmeyen API'ler Unicode sürümleri kullanmanızı öneririz.  
  
## <a name="when-not-to-use-pinvoke"></a>Ne zaman PInvoke kullanma  
 PInvoke kullanarak DLL'lerde tüm C stili işlevleri için uygun değil. Örneğin, bir işlev MakeSpecial mylib.dll gibi bildirilmiş var. varsayın:  
  
 `char * MakeSpecial(char * pszString);`  
  
 Visual C++ uygulamasında PInvoke kullanıyoruz, aşağıdakine benzer bir şey yazma:  
  
 `[DllImport("mylib")]`  
  
 `extern "C" String * MakeSpecial([MarshalAs(UnmanagedType::LPStr)] String ^);`  
  
 Zorluk MakeSpecial tarafından döndürülen yönetilmeyen dize için bellek silemiyoruz ' dir. PInvoke aracılığıyla çağrılan diğer işlevleri, kullanıcı tarafından bırakılmasına sahip olmayan bir iç arabellek için bir işaretçi döndürür. Bu durumda, IJW özelliğini kullanarak belirgin bir seçimdir.  
  
## <a name="limitations-of-pinvoke"></a>PInvoke sınırlamaları  
 Parametre olarak sürdü yerel işlevden işaretçinin aynısını döndüremez. Yerel bir işleve sıralanmış işaretçi için PInvoke tarafından döndürürse, Bellek Bozulması ve özel durum oluşması beklenebilir.  
  
```  
__declspec(dllexport)  
char* fstringA(char* param) {  
   return param;  
}  
```  
  
 Aşağıdaki örnek bu sorunun yaşandığı ve program doğru çıktıyı veriyor gibi görünse de, çıktı serbest bırakılmış bellekten geliyor.  
  
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
  
## <a name="marshaling-arguments"></a>Bağımsız değişkenler hazırlama  
 İle `PInvoke`, hiçbir hazırlama gerekli arasında yönetilen ve C++ yerel temel türler ile aynı formu. Örneğin, hiçbir sıralama veya çift ve çift Int32 ve int arasında gereklidir.  
  
 Ancak, aynı forma sahip olmayan türleri sıralamanız gerekir. Bu, char, dize ve yapı türleri içerir. Aşağıdaki tabloda çeşitli türleri için sıralayıcı tarafından kullanılan eşlemeleri gösterir:  
  
|wtypes.h|Visual C++|Visual C++/CLR ile|Ortak dil çalışma zamanı|  
|--------------|------------------|-----------------------------|-----------------------------|  
|İŞLEME|void *|void *|IntPtr, UIntPtr|  
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
|LPCSTR|char *|Dize ^ [in], StringBuilder ^ [ın, out]|Dize ^ [in], StringBuilder ^ [ın, out]|  
|LPCSTR|const char *|Dize ^|Dize|  
|LPWSTR|wchar_t *|Dize ^ [in], StringBuilder ^ [ın, out]|Dize ^ [in], StringBuilder ^ [ın, out]|  
|LPCWSTR|const wchar_t *|Dize ^|Dize|  
|KAYAN NOKTA|float|float|Tek|  
|ÇİFT|çift|çift|Çift|  
  
 Sıralayıcı otomatik olarak adresini yönetilmeyen bir işleve aktarılırsa çalışma zamanı yığında ayrılmış bellek sabitler. Sabitleme, atık toplayıcı ayrılan bellek bloğunu sıkıştırma sırasında geçmesini önler.  
  
 Bu konunun önceki bölümlerinde gösterilen örnekte DllImport CharSet parametresinin nasıl yönetilen dizelerini belirtir. sıralanmalıdır; Bu durumda, kullanıcılar için yerel tarafı için ANSI dizelerini sıralanmalıdır.  
  
 MarshalAs özniteliğini kullanarak yerel bir işleve bağımsız değişkenleri için hazırlama bilgileri belirtebilirsiniz. Bir dize sıralama için birkaç seçenek vardır * bağımsız değişken: BStr, ANSIBStr, TBStr, LPStr, LPWStr ve LPTStr. LPStr varsayılandır.  
  
 Bu örnekte, dize çift baytlık Unicode karakter dizesi olarak, LPWStr sıralanır. Çıktı Hello World ilk harfini değil! İkinci bayt sıralanmış dizenin null ve puts Bu dize sonu işaretçisi olarak yorumlar.  
  
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
  
 MarshalAs özniteliği System::Runtime:: InteropServices ad alanında ' dir. Öznitelik, dizileri gibi diğer veri türleriyle kullanılabilir.  
  
 Konuda daha önce belirtildiği gibi hazırlama kitaplığını yerel ve yönetilen ortamlar arasında verileri hazırlama, yeni, en iyi duruma getirilmiş bir yöntem sağlar. Daha fazla bilgi için bkz: [, genel bakış hazırlama c++](../dotnet/overview-of-marshaling-in-cpp.md).  
  
## <a name="performance-considerations"></a>Başarım Değerlendirmeleri  
 PInvoke sahip 10 ile 30 arasında bir yükü x86 çağrı başına yönergeler. Bu sabit maliyet yanı sıra, sıralama ek yük oluşturur. Yönetilen ve yönetilmeyen kodunda aynı gösterimi varsa blittable türleri arasında hiçbir hazırlama maliyeti yoktur. Örneğin, int ve Int32 arasında maliyeti yoktur.  
  
 Daha iyi performans için daha az veri çağrı başına sıralama daha fazla çağrı yerine mümkün olduğunca kadar veri sıralama daha az PInvoke çağrıları vardır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yerel ve.NET Birlikte Çalışabilirliği](../dotnet/native-and-dotnet-interoperability.md)