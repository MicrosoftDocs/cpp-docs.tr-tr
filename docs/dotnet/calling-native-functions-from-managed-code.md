---
title: Yönetilen Koddan Yerel İşlevleri Çağırma
ms.date: 11/04/2016
helpviewer_keywords:
- native functions called from managed code [C++]
- managed code [C++], interoperability
- platform invoke [C++], interoperability
- interoperabiliy [C++], calling native functions from managed code
- calling native functions from managed code
- interop [C++], calling native functions from managed code
ms.assetid: 982cef18-20d9-42b4-8242-a77fa65f2e36
ms.openlocfilehash: 50f40cc147daaa26a7fa4e607f0d4dd42cf22d61
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/10/2019
ms.locfileid: "74988662"
---
# <a name="calling-native-functions-from-managed-code"></a>Yönetilen Koddan Yerel İşlevleri Çağırma

Ortak dil çalışma zamanı, yönetilen kodun yerel dinamik bağlantı kitaplıklarında (DLL'ler) C stili işlevleri çağırmasına imkan tanıyan Platform Çağırma Hizmetleri veya PInvoke sağlar. Aynı veri sıralama, çalışma zamanıyla COM birlikte çalışabilirlik için ve "It Just Works" öğesi veya IJW, mekanizma için kullanılır.

Daha fazla bilgi için bkz.

- [C++'ta Açık PInvoke Kullanma (DllImport Özniteliği)](../dotnet/using-explicit-pinvoke-in-cpp-dllimport-attribute.md)

- [C++ Birlikte Çalışabilirliği Kullanma (Örtük PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md)

Bu bölümdeki örnekler sadece `PInvoke` öğesinin kullanımını gösterir. Yordam sıralama kodu yazmak yerine sıralama bilgilerini bildirimli olarak öznitelikler yoluyla sağladığınızdan `PInvoke`, özelleştirilmiş veri sıralamasını basitleştirebilir.

> [!NOTE]
>  Sıralama kitaplığı, en iyi duruma getirilmiş şekilde yerel ve yönetilen ortamlar arasında veri sıralamanın alternatif bir yolunu sağlar. Hazırlama Kitaplığı hakkında daha fazla bilgi için bkz. [ C++ sıralamaya genel bakış](../dotnet/overview-of-marshaling-in-cpp.md) . Sıralama kitaplığı işlevler için değil yalnızca veriler için kullanılabilir.

## <a name="pinvoke-and-the-dllimport-attribute"></a>PInvoke ve DllImport Özniteliği

Aşağıdaki örnek bir Visual C++ programında `PInvoke` öğesinin kullanımını gösterir. Yerel işlev giriş/çıkışları msvcrt.dll'de tanımlanır. DllImport özniteliği giriş/çıkış bildirimi için kullanılır.

```cpp
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

Aşağıdaki örnek, önceki örneğe eşdeğerdir, ancak IJW kullanır.

```cpp
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

- Programın kullandığı yönetilmeyen API'lara ilişkin `DLLImport` öznitelik bildirimlerini yazmaya gerek yoktur. Üstbilgi dosyasını ve bağlantıyı içe aktarma kitaplığıyla birlikte ekleyin.

- IJW mekanizması biraz daha hızlıdır (örneğin, IJW saplamalarının veri öğelerini sabitlemesi veya kopyalaması gerekmez çünkü bunlar açıkça geliştirici tarafından yapılır).

- Performans sorunlarını açıkça gösterir. Bu durumda, aslında bir Unicode dizesini bir ANSI dizesine çeviriyorsunuz ve görevli bellek ayırmaya ve ayırmayı kaldırmaya sahipsiniz. Bu durumda, IJW kullanarak kodu yazan geliştirici `_putws` ve `PtrToStringChars` öğesini çağırmanın performans için daha iyi olacağını görecektir.

- Aynı veriyi kullanarak birçok yönetilmeyen API çağırırsanız, bunu bir kez hazırlamak ve hazırlanmış kopyayı geçirmek, her seferinde yeniden hazırlamaktan çok daha fazla verimlidir.

### <a name="disadvantages-of-ijw"></a>IJW Dezavantajları

- Sıralama, öznitelikler (çoğu zaman uygun varsayılanlara sahiptir) tarafından değil, kod içinde açıkça belirtilmelidir.

- Sıralama kodu uygulama mantığının akışında daha bozucu olduğu satır içidir.

- Açık sıralama API'ları 32-bit ila 64-bit taşınabilirlik için `IntPtr` türlerini döndürdüğünden, ek `ToPointer` çağrıları kullanmanız gerekir.

C++ tarafından sunulan belirli yöntem, bazı ek karmaşıklıklar içerir ancak daha etkin ve açık bir yöntemdir.

Uygulama ağırlıklı olarak yönetilmeyen veri türleri kullanıyorsa veya .NET Framework API'larından daha fazla yönetilmeyen API'ları çağırıyorsa, IJW özelliğini kullanmanızı öneririz. Çoğunlukla yönetilen uygulamada nadiren yönetilmeyen API çağırmak için gereken seçim daha inceliklidir.

## <a name="pinvoke-with-windows-apis"></a>Windows API'ları içeren PInvoke

PInvoke, Windows'daki işlevleri çağırmak için uygundur.

Bu örnekte, bir Visual C++ programı Win32 API'sının parçası olan MessageBox işleviyle birlikte çalışır.

```cpp
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

Çıktı, PInvoke Testi başlığına sahip olan ve Hello World! metnini içeren bir ileti kutusudur.

Sıralama bilgileri DLL'deki işlevleri aramak için PInvoke tarafından da kullanılır. user32.dll öğesinde aslında MessageBox işlevi yoktur, ancak CharSet=CharSet::Ansi PInvoke'un Unicode sürümü olan MessageBoxW yerine ANSI sürümü olan MessageBoxA öğesini kullanmasına olanak verir. Genel olarak, .NET Framework dize nesnelerinin yerel Unicode biçimlerini ANSI öğesine çevirme yükünü ortadan kaldıracağından yönetilmeyen API'ların Unicode sürümlerini kullanmanızı öneririz.

## <a name="when-not-to-use-pinvoke"></a>PInvoke Ne Zaman Kullanılmaz?

PInvoke kullanma, DLL'lerdeki tüm C-stili işlevler için uygun değildir. Örneğin, aşağıdaki gibi belirtilen bir mylib.dll içinde bir MakeSpecial işlevinin bulunduğunu varsayın:

`char * MakeSpecial(char * pszString);`

Visual C++ uygulamasında PInvoke işlevini kullanırsak, aşağıdakine benzer bir şey yazabiliriz:

```cpp
[DllImport("mylib")]
extern "C" String * MakeSpecial([MarshalAs(UnmanagedType::LPStr)] String ^);
```

Buradaki zorluk MakeSpecial tarafından döndürülen yönetilmeyen dize için belleği silemememizdir. PInvoke aracılığıyla çağrılan diğer işlevler kullanıcı tarafından kaldırılması gerekmeyen dahili arabelleğe ilişkin bir işaretçi döndürür. Bu durumda belirgin seçim, IJW özelliğini kullanmaktır.

## <a name="limitations-of-pinvoke"></a>PInvoke Sınırlamaları

Parametre olarak aldığınız yerel bir işlevden işaretçinin aynısını döndüremezsiniz. Yerel bir işlev PInvoke tarafından kendisine sıralanmış işaretçiyi döndürürse, bellek bozulması ve özel durumlar oluşması beklenebilir.

```cpp
__declspec(dllexport)
char* fstringA(char* param) {
   return param;
}
```

Aşağıdaki örnek bu sorunu gösterir ve program doğru çıktıyı veriyor gibi görünse bile çıktı serbest bırakılan bellekten gelmektedir.

```cpp
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

## <a name="marshaling-arguments"></a>Bağımsız Değişkenleri Sıralama

`PInvoke` ile aynı forma sahip yönetilen ve C++ yerel temel türler arasında sıralamaya gerek yoktur. Örneğin, Int32 ve int arasında veya Double ve double arasında herhangi bir sıralama yapılması gerekmez.

Ancak, aynı forma sahip olmayan türleri sıralamanız gerekir. Bu; char, string ve struct türlerini içerir. Aşağıdaki tablo, çeşitli türler için sıralayıcı tarafından kullanılan eşlemeleri gösterir:

|wtypes.h|Visual C++|/clr öğesine sahip Visual C++|Ortak dil çalışma zamanı|
|--------------|------------------|-----------------------------|-----------------------------|
|TANITICI|void \*|void \*|IntPtr, UIntPtr|
|BYTE|unsigned char|unsigned char|Bayt|
|SHORT|short|short|Int16|
|WORD|imzasız short|imzasız short|UInt16|
|INT|int|int|Int32|
|UINT|unsigned int|unsigned int|UInt32|
|LONG|long|long|Int32|
|BOOL|long|bool|Boole değeri|
|DWORD|imzasız long|imzasız long|UInt32|
|ULONG|imzasız long|imzasız long|UInt32|
|CHAR|char|char|Char|
|LPCSTR|Char \*|String ^ [in], StringBuilder ^ [in, out]|String ^ [in], StringBuilder ^ [in, out]|
|LPCSTR|const char \*|String ^|Dize|
|LPWSTR|wchar_t \*|String ^ [in], StringBuilder ^ [in, out]|String ^ [in], StringBuilder ^ [in, out]|
|LPCWSTR|const wchar_t \*|String ^|Dize|
|FLOAT|float|float|Tek|
|DOUBLE|çift|çift|Çift|

Adresi yönetilmeyen bir işleve geçirilirse sıralayıcı otomatik olarak çalışma zamanı yığınına ayrılmış belleği sabitler. Sabitleme, çöp toplayıcısının ayrılan bellek bloğunu sıkıştırma sırasında taşımasını engeller.

Bu konunun önceki bölümlerinde gösterilen örnekte, DllImport öğesinin CharSet parametresi yönetilen Dizeler'in nasıl sıralanması gerektiğini belirtir; bu durumda bunlar yerel taraf için ANSI dizelerine sıralanmalıdır.

MarshalAs özniteliğini kullanılarak bir yerel işlevin tek tek bağımsız değişkenlerinin sıralama bilgilerini belirtebilirsiniz. Bir dize \* bağımsız değişkeni sıralama için birkaç seçenek vardır: BStr, ANSIBStr, TBStr, LPStr, LPWStr ve LPTStr. Varsayılan, LPStr'dir.

Bu örnekte, dize çift baytlık Unicode karakter dizesi, LPWStr olarak sıralanır. Çıktı Merhaba Dünya ilk harftir! sıralanan dizenin ikinci baytı null olduğundan ve koyar bunu dize sonu işaretçisi olarak yorumlar.

```cpp
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

MarshalAs özniteliği System::Runtime::InteropServices ad alanındadır. Öznitelik, diziler gibi diğer veri türleri ile kullanılabilir.

Bu konuda daha önce belirtildiği gibi sıralama kitaplığı, yerel ve yönetilen ortamlar arasında verileri sıralamak için yeni, en iyi duruma getirilmiş bir yöntem sağlar. Daha fazla bilgi için bkz. [' de C++sıralamaya genel bakış ](../dotnet/overview-of-marshaling-in-cpp.md).

## <a name="performance-considerations"></a>Performansla İlgili Konular

PInvoke, çağrı başına 10 ila 30 x86 yönergeleri yüküne sahiptir. Bu sabit maliyete ek olarak, sıralama ek yük oluşturur. Yönetilen ve yönetilmeyen kod içinde aynı gösterimi içeren taşınabilir türler arasında hiçbir sıralama maliyeti yoktur. Örneğin, int ve Int32 arasında dönüştürme maliyeti yoktur.

Daha iyi performans için, çağrı başına daha az veri sıralayan daha fazla çağrı yerine, mümkün olan en fazla veriyi sıralayan daha az PInvoke çağrısına sahip olun.

## <a name="see-also"></a>Ayrıca bkz.

[Yerel ve.NET Birlikte Çalışabilirliği](../dotnet/native-and-dotnet-interoperability.md)
