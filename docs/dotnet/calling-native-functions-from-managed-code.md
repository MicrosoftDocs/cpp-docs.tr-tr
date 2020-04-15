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
ms.openlocfilehash: 0cdd5db4fae8d9167fa9ab1aeb6a4e8cbfe76ded
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372519"
---
# <a name="calling-native-functions-from-managed-code"></a>Yönetilen Koddan Yerel İşlevleri Çağırma

Ortak dil çalışma süresi, yönetilen kodun yerel dinamik bağlantılı kitaplıklarda (DLL) C stili işlevleri ni aramasını sağlayan Platform Çağırma Hizmetleri veya PInvoke sağlar. Aynı veri işleme çalışma süresi ile COM birlikte çalışabilirlik ve "It Just Works" veya IJW, mekanizma için kullanılır.

Daha fazla bilgi için bkz.

- [C++'da Açık PInvoke kullanma (DllImport Özniteliği)](../dotnet/using-explicit-pinvoke-in-cpp-dllimport-attribute.md)

- [C++ Interop Kullanma (Örtülü PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md)

Bu bölümdeki örnekler sadece `PInvoke` nasıl kullanılabileceğini göstermektedir. `PInvoke`yordam mareşalkodu yazmak yerine özniteliklerde açıklayıcı bilgi verdiğiniz için özelleştirilmiş veri mareşalliğini basitleştirebilir.

> [!NOTE]
> Mareşal kitaplığı, verileri yerel ve yönetilen ortamlar arasında en iyi duruma getirilmiş bir şekilde mareşallemek için alternatif bir yol sağlar. Mareşallik kitaplığı hakkında daha fazla bilgi için [C++'da Mareşallik](../dotnet/overview-of-marshaling-in-cpp.md) Bölümü'ne genel bakış. Mareşal kitaplığı yalnızca veriler için kullanılabilir ve işlevler için değil.

## <a name="pinvoke-and-the-dllimport-attribute"></a>PInvoke ve DllImport Özniteliği

Aşağıdaki örnek, Visual `PInvoke` C++ programının kullanımını gösterir. Yerel fonksiyon koyar msvcrt.dll tanımlanır. DllImport özniteliği puts bildirimi için kullanılır.

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

Aşağıdaki örnek önceki örneğe eşdeğerdir, ancak IJW kullanır.

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

- Programın kullandığı yönetilmeyen `DLLImport` API'ler için öznitelik bildirimleri yazmaya gerek yoktur. Üstbilgi dosyasını ve alma kitaplığıyla bağlantı kurmanın tek et.

- IJW mekanizması biraz daha hızlıdır (örneğin, Geliştirici tarafından açıkça yapıldığı için iJW saplamalarının veri öğelerini sabitleme veya kopyalama gereksinimini denetlemesi gerekmez).

- Performans sorunlarını açıkça gösteriyor. Bu durumda, unicode dizesinden ANSI dizesine çeviri yaptığınız ve görevli bellek ayırma ve ayırmanız olması. Bu durumda, IJW kullanarak kodu yazan bir `_putws` geliştirici `PtrToStringChars` arama ve kullanmanın performans için daha iyi olacağını fark eder.

- Aynı verileri kullanarak birçok yönetilmeyen API'yi arıyorsanız, bir kez mareşallik yapmak ve mareşal kopyayı geçirmek her seferinde yeniden genelleme yapmaktan çok daha etkilidir.

### <a name="disadvantages-of-ijw"></a>IJW dezavantajları

- Mareşallik öznitelikler yerine (genellikle uygun varsayılanlara sahip) açıkça kod olarak belirtilmelidir.

- Mareşalkodu, uygulama mantığının akışında daha invaziv olduğu satır da dır.

- Açık marshaling API'ler 32-64 bit taşınabilirlik için döndürülebilir, `IntPtr` ek `ToPointer` aramalar kullanmanız gerekir.

C++ tarafından maruz belirli yöntem, bazı ek karmaşıklık pahasına, daha verimli, açık bir yöntemdir.

Uygulama çoğunlukla yönetilmeyen veri türleri kullanıyorsa veya .NET Framework API'lerinden daha fazla yönetilmeyen API'ler gerektiriyorsa, IJW özelliğini kullanmanızı öneririz. Çoğunlukla yönetilen bir uygulamada zaman zaman yönetilmeyen bir API çağırmak için seçim daha ince.

## <a name="pinvoke-with-windows-apis"></a>Windows API'leri ile PInvoke

PInvoke, Windows'daki arama işlevleri için uygundur.

Bu örnekte, Visual C++ programı Win32 API'sinin bir parçası olan MessageBox işlevi ile birlikte çalışır.

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

Çıktı, PInvoke Testi başlığına sahip ve Hello World!.

Mareşal bilgileri, PInvoke tarafından DLL'deki işlevleri aramak için de kullanılır. user32.dll'de aslında MessageBox işlevi yoktur, ancak CharSet=CharSet::Ansi, PInvoke'ın Unicode sürümü olan MessageBoxW yerine ANSI sürümü olan MessageBoxA'yı kullanmasını sağlar. Genel olarak, yönetilmeyen API'lerin Unicode sürümlerini kullanmanızı öneririz, çünkü bu, .NET Framework dize nesnelerinin yerel Unicode biçiminden ANSI'ye olan çeviri ek yüküne neden olabilir.

## <a name="when-not-to-use-pinvoke"></a>PInvoke Kullanılmadığında

PInvoke kullanmak, DL'lerde bulunan tüm C stili işlevler için uygun değildir. Örneğin, mylib.dll'de aşağıdaki gibi beyan edilen MakeSpecial işlevi olduğunu varsayalım:

`char * MakeSpecial(char * pszString);`

Görsel C++ uygulamasında PInvoke kullanırsak, aşağıdakilere benzer bir şey yazabiliriz:

```cpp
[DllImport("mylib")]
extern "C" String * MakeSpecial([MarshalAs(UnmanagedType::LPStr)] String ^);
```

Buradaki zorluk, MakeSpecial tarafından döndürülen yönetilmeyen dize için belleği silemesek de. PInvoke aracılığıyla çağrılan diğer işlevler, bir işaretçiyi kullanıcı tarafından ayrılması gerekmeyen bir iç arabelleğe döndürür. Bu durumda, IJW özelliğini kullanarak bariz bir seçimdir.

## <a name="limitations-of-pinvoke"></a>PInvoke sınırlamaları

Parametre olarak aldığınız yerel bir işlevden aynı işaretçiyi döndüremezsiniz. Yerel bir işlev, PInvoke tarafından kendisine marshaled olan işaretçi döndürürse, bellek bozulması ve özel durumlar ortaya çıkabilir.

```cpp
__declspec(dllexport)
char* fstringA(char* param) {
   return param;
}
```

Aşağıdaki örnek bu sorunu sergiler ve program doğru çıktı vermek gibi görünse de, çıktı serbest bırakılmış bellekgeliyor.

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

## <a name="marshaling-arguments"></a>Marshaling Argümanlar

Ile, `PInvoke`aynı forma sahip yönetilen ve C++ yerel ilkel türleri arasında hiçbir mareşalgerekli değildir. Örneğin, Int32 ile int arasında veya Çift ve Çift arasında bir mareşallik gerekmez.

Ancak, aynı forma sahip olmayan türleri mareşal gerekir. Bu char, dize ve yapı türlerini içerir. Aşağıdaki tablo, mareşal tarafından çeşitli türler için kullanılan eşlemeleri gösterir:

|wtypes.h|Visual C++|/clr ile Görsel C++|Ortak dil çalışma zamanı|
|--------------|------------------|-----------------------------|-----------------------------|
|Işlemek|Void\*|Void\*|IntPtr, UIntPtr|
|BYTE|unsigned char|unsigned char|Bayt|
|Kısa|short|short|Int16|
|WORD|imzasız short|imzasız short|UInt16|
|INT|int|int|Int32|
|UINT|unsigned int|unsigned int|UInt32|
|Uzun|long|long|Int32|
|Bool|long|bool|Boole|
|DWORD|imzasız long|imzasız long|UInt32|
|Ulong|imzasız long|imzasız long|UInt32|
|Char|char|char|Char|
|Lpstr|Char\*|String ^ [in], StringBuilder ^ [içinde, dışarı]|String ^ [in], StringBuilder ^ [içinde, dışarı]|
|LPCSTR|const char\*|Dize ^|Dize|
|Lpwstr|Wchar_t\*|String ^ [in], StringBuilder ^ [içinde, dışarı]|String ^ [in], StringBuilder ^ [içinde, dışarı]|
|LPCWSTR|const wchar_t\*|Dize ^|Dize|
|Float|float|float|Tek|
|Çift|double|double|Çift|

Mareşal, adresi yönetilmeyen bir işleve geçirilirse, çalışma zamanı yığınında ayrılan belleği otomatik olarak sabitler. Sabitleme, çöp toplayıcısının sıkıştırma sırasında ayrılan bellek bloğunu hareket ettirmesini önler.

Bu konuda daha önce gösterilen örnekte, DllImport'un CharSet parametresi, yönetilen Dizelerin nasıl marshaled edilmesi gerektiğini belirtir; bu durumda, onlar yerli tarafı için ANSI dizeleri marshaled olmalıdır.

Mareşal özniteliğini kullanarak yerel bir işlevin tek tek bağımsız bağımsız bağımsız değişkenleri için mareşal bilgileri belirtebilirsiniz. Bir String \* bağımsız değişkenini mareşallik etmek için çeşitli seçenekler vardır: BStr, ANSIBStr, TBStr, LPStr, LPWStr ve LPTStr. Varsayılan LPStr'dir.

Bu örnekte, dize çift bayt Unicode karakter dizesi, LPWStr olarak marshaled. Çıkış Hello World ilk harfi! çünkü mareşal dizesinin ikinci baytı null'dur ve bunu dize sonu işaretçisi olarak yorumluyor.

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

Mareşalöz özniteliği Sistemde::Runtime::InteropServices ad alanı. Öznitelik diziler gibi diğer veri türleri ile kullanılabilir.

Daha önce konu belirtildiği gibi, mareşal kitaplığı yerel ve yönetilen ortamlar arasında veri mareşallik yeni, optimize yöntemi sağlar. Daha fazla bilgi için [C++'da Mareşallik Genel Bakış'a](../dotnet/overview-of-marshaling-in-cpp.md)bakın.

## <a name="performance-considerations"></a>Başarım Değerlendirmeleri

PInvoke'ın her çağrı başına 10 ila 30 x86 yönergesi içeren bir yükü vardır. In addition to this fixed cost, marshaling creates additional overhead. Yönetilen ve yönetilmeyen kodda aynı gösterime sahip blittable türleri arasında mareşal maliyeti yoktur. Örneğin, int ve Int32 arasında çevirmek için hiçbir maliyet yoktur.

Daha iyi performans için, çağrı başına daha az veri mareşal daha fazla çağrı yerine, mümkün olduğunca çok veri mareşal daha az PInvoke çağrıları var.

## <a name="see-also"></a>Ayrıca bkz.

[Yerel ve.NET Birlikte Çalışabilirliği](../dotnet/native-and-dotnet-interoperability.md)
