---
description: 'Hakkında daha fazla bilgi edinin: yönetilen koddan yerel Işlevleri çağırma'
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
ms.openlocfilehash: b037027f863ff12ac83429715cdf50bff4549a93
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97282542"
---
# <a name="calling-native-functions-from-managed-code"></a>Yönetilen Koddan Yerel İşlevleri Çağırma

Ortak dil çalışma zamanı, yönetilen kodun yerel dinamik bağlantılı kitaplıklarda (dll 'Ler) C stili işlevleri çağırmasını sağlayan platform çağırma hizmetleri veya PInvoke sağlar. Aynı veri sıralaması, çalışma zamanıyla COM birlikte çalışabilirliği ve "It yalnızca çalışıyor" veya ıJW, mekanizması için kullanılır.

Daha fazla bilgi için bkz:

- [C++ ' ta açık PInvoke kullanma (DllImport özniteliği)](../dotnet/using-explicit-pinvoke-in-cpp-dllimport-attribute.md)

- [C++ birlikte çalışabilirliği kullanma (örtük PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md)

Bu bölümdeki örneklerde yalnızca nasıl `PInvoke` kullanılabileceği gösterilmektedir. `PInvoke` , yordamsal sıralama kodu yazmak yerine sıralama bilgilerini bildirimli olarak öznitelikler halinde sağladığınızdan, özelleştirilmiş veri hazırlamayı kolaylaştırabilir.

> [!NOTE]
> Sıralama kitaplığı, yerel ve yönetilen ortamlar arasında iyileştirilmiş bir şekilde veri sıralaması için alternatif bir yol sağlar. Sıralama kitaplığı hakkında daha fazla bilgi için bkz. [C++ ' da sıralamaya genel bakış](../dotnet/overview-of-marshaling-in-cpp.md) . Sıralama kitaplığı, işlevleri için değil, yalnızca veriler için kullanılabilir.

## <a name="pinvoke-and-the-dllimport-attribute"></a>PInvoke ve DllImport özniteliği

Aşağıdaki örnek, `PInvoke` bir Visual C++ programında kullanımını gösterir. Yerel işlev koyar msvcrt.dll tanımlanmıştır. DllImport özniteliği, yerleştirmenin bildirimi için kullanılır.

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

Aşağıdaki örnek, önceki örneğe eşdeğerdir, ancak ıJW kullanır.

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

- `DLLImport`Programın kullandığı yönetilmeyen API 'ler için öznitelik bildirimleri yazmanız gerekmez. Yalnızca başlık dosyasını ve bağlantıyı içeri aktarma kitaplığıyla dahil edin.

- IJW mekanizması biraz daha hızlıdır (örneğin, ıJW saplamalarının, geliştirici tarafından açıkça yapıldığından, veri öğelerini sabitleme veya kopyalama gereksinimini denetlemesi gerekmez).

- Performans sorunlarını net bir şekilde gösterir. Bu durumda, bir Unicode dizesinden bir ANSI dizesine çevirin ve bir görevlisi bellek ayırma ve ayırmayı kaldırma olgusunun olması gerekir. Bu durumda, ıJW kullanarak kodu yazan bir geliştirici, çağırmanın `_putws` ve kullanmanın `PtrToStringChars` performans açısından daha iyi olacağını fark ediyor.

- Aynı verileri kullanarak çok sayıda yönetilmeyen API çağırırsanız, onu bir kez sıralama ve sıralanmış kopyayı geçirme her seferinde yeniden hazırlamayı çok daha etkilidir.

### <a name="disadvantages-of-ijw"></a>IJW dezavantajları

- Sıralama, öznitelikler (genellikle uygun varsayılanlara sahiptir) yerine doğrudan kodda belirtilmelidir.

- Sıralama kodu, uygulama mantığının akışında daha fazla yer aldığı satır içidir.

- Açık sıralama API 'Leri `IntPtr` 32 bit-64-bit taşınabilirlik için türler döndürdüğü için, fazladan çağrılar kullanmanız gerekir `ToPointer` .

C++ tarafından sunulan belirli bir yöntem, daha verimli, açık bir yöntemdir ve bazı ek karmaşıklık maliyetlidir.

Uygulama ağırlıklı olarak yönetilmeyen veri türlerini kullanıyorsa veya .NET Framework API 'lerden daha fazla yönetilmeyen API çağırırsa, ıJW özelliğini kullanmanızı öneririz. Genellikle yönetilen bir uygulamada zaman zaman yönetilmeyen bir API çağırmak için, tercih daha hafif olur.

## <a name="pinvoke-with-windows-apis"></a>Windows API 'Leri ile PInvoke

PInvoke, Windows 'da işlevleri çağırmak için uygundur.

Bu örnekte, bir Visual C++ programı Win32 API parçası olan MessageBox işleviyle birlikte çalışır.

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

Çıktı, PInvoke test başlığına sahip olan ve Merhaba Dünya! metnini içeren bir ileti kutusudur.

Sıralama bilgileri ayrıca PInvoke tarafından DLL 'deki işlevleri aramak için kullanılır. user32.dll aslında bir MessageBox işlevi yoktur, ancak CharSet = CharSet:: ansi, PInvoke 'un Unicode sürümü olan MessageBoxW yerine, ANSI sürümünü kullanmasını sağlar. Genel olarak, yönetilmeyen API 'lerin Unicode sürümlerini kullanmanızı öneririz çünkü bu, .NET Framework dize nesnelerinin yerel Unicode biçiminden ANSI 'ye çeviri yükünü ortadan kaldırır.

## <a name="when-not-to-use-pinvoke"></a>PInvoke ne zaman kullanılmaz?

PInvoke kullanmak, dll 'Lerdeki tüm C stili işlevlere uygun değildir. Örneğin, aşağıdaki şekilde bildirildiği mylib.dll bir MakeSpecial işlevi olduğunu varsayalım:

`char * MakeSpecial(char * pszString);`

Visual C++ uygulamasında PInvoke kullandığımızda aşağıdakine benzer bir değer yazabilirsiniz:

```cpp
[DllImport("mylib")]
extern "C" String * MakeSpecial([MarshalAs(UnmanagedType::LPStr)] String ^);
```

Buradaki zorluk, MakeSpecial tarafından döndürülen yönetilmeyen dize için belleği silemediğimiz bir sorun. PInvoke aracılığıyla çağrılan diğer işlevler, Kullanıcı tarafından serbest bırakılmaması gereken bir iç arabelleğe yönelik bir işaretçi döndürür. Bu durumda, ıJW özelliğinin kullanılması belirgin bir seçimdir.

## <a name="limitations-of-pinvoke"></a>PInvoke sınırlamaları

Parametre olarak aldığınız yerel bir işlevden aynı tam işaretçiyi geri dönemezsiniz. Yerel bir işlev, PInvoke tarafından kendisine sıralanmış işaretçiyi döndürürse, bellek bozulması ve özel durumlar olabilir.

```cpp
__declspec(dllexport)
char* fstringA(char* param) {
   return param;
}
```

Aşağıdaki örnek bu sorunu sergiler ve program doğru çıktıyı verebilir gibi görünse de çıkış serbest bırakılmış bellekten geliyor olabilir.

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

## <a name="marshaling-arguments"></a>Bağımsız değişkenleri hazırlama

İle `PInvoke` , aynı form ile yönetilen ve C++ yerel ilkel türleri arasında sıralama gerekmez. Örneğin, Int32 ve int arasında ya da Double ve Double arasında sıralama gerekmez.

Ancak, aynı forma sahip olmayan türleri de sıramalısınız. Bu, Char, String ve struct türlerini içerir. Aşağıdaki tabloda, çeşitli türler için sıralayıcı tarafından kullanılan eşlemeler gösterilmektedir:

|WTypes. h|Visual C++|/Clr ile Visual C++|Ortak dil çalışma zamanı|
|--------------|------------------|-----------------------------|-----------------------------|
|TUTAMAÇLARDAN|Kağıt \*|Kağıt \*|IntPtr, UIntPtr|
|BYTE|unsigned char|unsigned char|Bayt|
|KıSADıR|short|short|Int16|
|WORD|imzasız short|imzasız short|UInt16|
|INT|int|int|Int32|
|UINT|unsigned int|unsigned int|UInt32|
|KALACAĞıNı|long|long|Int32|
|BOOL|long|bool|Boole|
|DWORD|imzasız long|imzasız long|UInt32|
|'TUR|imzasız long|imzasız long|UInt32|
|CHAR|char|char|Char|
|LPSTR|Char \*|Dize ^ [in], StringBuilder ^ [in, out]|Dize ^ [in], StringBuilder ^ [in, out]|
|LPCSTR|const char \*|Dize ^|Dize|
|LPWSTR|wchar_t \*|Dize ^ [in], StringBuilder ^ [in, out]|Dize ^ [in], StringBuilder ^ [in, out]|
|LPCWSTR|const wchar_t \*|Dize ^|Dize|
|FLOAT|float|float|Tek|
|ÇIFT|double|double|Çift|

Sıralayıcısı, adresi yönetilmeyen bir işleve geçirilirse, çalışma zamanı yığınında ayrılan belleği otomatik olarak sabitler. Sabitleme, çöp toplayıcısının, sıkıştırma sırasında ayrılan bellek bloğunu taşımasını engeller.

Bu konunun önceki kısımlarında gösterilen örnekte, DllImport karakter kümesi parametresi yönetilen dizelerin nasıl sıralanması gerektiğini belirtir; Bu durumda, yerel taraf için ANSI dizelerine sıralanmalıdır.

MarshalAs özniteliğini kullanarak, yerel bir işlevin bağımsız bağımsız değişkenleri için sıralama bilgilerini belirtebilirsiniz. Dize bağımsız değişkenini sıralamaya yönelik çeşitli seçimler vardır \* : BSTR, ANSIBStr, TBStr, LPStr, LPWStr ve LPTStr. Varsayılan değer LPStr 'dir.

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

MarshalAs özniteliği System:: Runtime:: InteropServices ad alanında bulunur. Özniteliği diziler gibi diğer veri türleriyle birlikte kullanılabilir.

Bu konuda daha önce belirtildiği gibi, hazırlama kitaplığı, yerel ve yönetilen ortamlar arasında veri hazırlama için yeni ve iyileştirilmiş bir yöntem sağlar. Daha fazla bilgi için bkz. [C++ ' da sıralamaya genel bakış](../dotnet/overview-of-marshaling-in-cpp.md).

## <a name="performance-considerations"></a>Başarım Değerlendirmeleri

PInvoke, çağrı başına 10 ila 30 x86 arasındaki yönergeleri içerir. Bu sabit maliyete ek olarak, sıralama ek yük oluşturur. Yönetilen ve yönetilmeyen koddaki aynı gösterimine sahip blittable türleri arasında sıralama maliyeti yoktur. Örneğin, int ve Int32 arasında çevrilecek bir maliyet yoktur.

Daha iyi performans için, çağrı başına daha az veri sıralaması yapan daha fazla çağrı yerine mümkün olduğunca çok veri sıralaması yapan daha az PInvoke çağrısı vardır.

## <a name="see-also"></a>Ayrıca bkz.

[Yerel ve .NET birlikte çalışabilirliği](../dotnet/native-and-dotnet-interoperability.md)
