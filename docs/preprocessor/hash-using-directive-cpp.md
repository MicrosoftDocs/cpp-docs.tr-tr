---
title: '#using yönergesi (C++/CLI)'
ms.date: 08/29/2019
f1_keywords:
- friend_as_cpp
- '#using'
- friend_as
- '#using_cpp'
helpviewer_keywords:
- using directive (#using)
- '#using directive'
- LIBPATH environment variable
- preprocessor, directives
ms.assetid: 870b15e5-f361-40a8-ba1c-c57d75c8809a
ms.openlocfilehash: 0245eb15219585421be83def0258415ab4b573b6
ms.sourcegitcommit: c1fd917a8c06c6504f66f66315ff352d0c046700
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/16/2020
ms.locfileid: "90684267"
---
# <a name="using-directive-ccli"></a>#using yönergesi (C++/CLı)

Meta verileri [/clr](../build/reference/clr-common-language-runtime-compilation.md)ile derlenen bir programa içeri aktarır.

## <a name="syntax"></a>Syntax

> **`#using`***Dosya* [ **`as_friend`** ]

### <a name="parameters"></a>Parametreler

*dosyasýný*\
Bir Microsoft ara dili (MSIL) *`.dll`* , *`.exe`* , *`.netmodule`* veya *`.obj`* dosyası. Örneğin,

`#using <MyComponent.dll>`

**`as_friend`**\
*Dosyadaki* tüm türlerin erişilebilir olduğunu belirtir. Daha fazla bilgi için bkz. [arkadaş derlemeler (C++)](../dotnet/friend-assemblies-cpp.md).

## <a name="remarks"></a>Açıklamalar

*Dosya* , yönetilen veriler ve yönetilen yapılar için içeri aktardığınız bir Microsoft ara DILI (MSIL) dosyası olabilir. Bir DLL bir derleme bildirimi içeriyorsa, bildirimde başvurulan tüm dll 'Ler içeri aktarılır. Oluşturmakta olduğunuz derleme meta verileri bir derleme başvurusu *olarak listeler.*

Belki de *Dosya* bir derleme içermiyor (*Dosya* bir modüldür) ve geçerli (derleme) uygulamasındaki modülden tür bilgilerini kullanmayı düşünmüyorsanız. Modülün, [/ASSEMBLYMODULE](../build/reference/assemblymodule-add-a-msil-module-to-the-assembly.md)kullanarak derlemenin bir parçası olduğunu gösterebilirsiniz. Ardından modüldeki türler derlemeye başvuruda bulunan herhangi bir uygulama için kullanılabilir hale gelir.

Kullanımına alternatif olarak **`#using`** [/Fu](../build/reference/fu-name-forced-hash-using-file.md) derleyici seçeneği vardır.

geçirilen. exe derlemeleri **`#using`** .NET Visual Studio derleyicilerinin (örneğin Visual Basic veya Visual C#) biri kullanılarak derlenmesi gerekir.  İle derlenen bir. exe derlemesinden meta verilerin içeri aktarılması girişimi **`/clr`** , dosya yükleme özel durumuyla sonuçlanır.

> [!NOTE]
> İle başvurulan bir bileşen, **`#using`** derleme zamanında içeri aktarılan dosyanın farklı bir sürümüyle çalıştırılabilir, böylece bir istemci uygulaması beklenmedik sonuçlara neden olur.

Derleyicinin bir derlemede (modül değil) bir türü tanımasını sağlamak için, türün çözümlenmesinin zorunlu olması gerekir. Örneğin, türü bir örnek tanımlayarak bu uygulamayı zorlayabilirsiniz. Derleyici için bir derlemede tür adlarını çözümlemek için başka yollar vardır. Örneğin, derlemedeki bir türden devralma durumunda tür adı derleyici tarafından bilinir.

Kullanılan kaynak kodundan oluşturulan meta verileri içeri aktarırken [`__declspec(thread)`](../cpp/thread.md) , iş parçacığı semantiği meta verilerde kalıcı olmaz. Örneğin, ile belirtilen bir değişken, **`__declspec(thread)`** .NET Framework ortak dil çalışma zamanı için oluşturulmuş bir programda derlenir ve sonra ile içeri aktarılırsa **`#using`** , **`__declspec(thread)`** değişken üzerinde semantiğe sahip olmaz.

Tarafından başvurulan bir dosyadaki tüm içeri aktarılan türler (hem yönetilen hem de yerel) **`#using`** kullanılabilir, ancak derleyici yerel türleri tanımlar değil, bildirim olarak değerlendirir.

İle derleme sırasında mscorlib.dll otomatik olarak başvurulur **`/clr`** .

LıBPATH ortam değişkeni, derleyicinin geçilen dosya adlarını çözümlediğinde aranacağı dizinleri belirtir **`#using`** .

Derleyici, aşağıdaki yol boyunca başvuruları arar:

- Bildiriminde belirtilen bir yol **`#using`** .

- Geçerli dizin.

- .NET Framework sistem dizini.

- Derleyici seçeneğiyle eklenen dizinler [`/AI`](../build/reference/ai-specify-metadata-directories.md) .

- LIBPATH ortam değişkenindeki dizinler.

## <a name="examples"></a>Örnekler

Bir üçüncü derlemeye başvuran ikinci bir derlemeye başvuran bir derleme derleyebilirsiniz. Yalnızca kendi türlerinden birini açık olarak kullanırsanız, yalnızca birinci derlemeden üçüncü derlemeye başvuru yapmanız gerekir.

```cpp
// using_assembly_A.cpp
// compile with: /clr /LD
public ref class A {};
```

```cpp
// using_assembly_B.cpp
// compile with: /clr /LD
#using "using_assembly_A.dll"
public ref class B {
public:
   void Test(A a) {}
   void Test() {}
};
```

Aşağıdaki örnekte, derleyici *using_assembly_A.dll*başvuru hakkında bir hata bildirmez çünkü program *using_assembly_A. cpp*içinde tanımlı türlerden hiçbirini kullanmaz.

```cpp
// using_assembly_C.cpp
// compile with: /clr
#using "using_assembly_B.dll"
int main() {
   B b;
   b.Test();
}
```

## <a name="see-also"></a>Ayrıca bkz.

[Ön işlemci yönergeleri](../preprocessor/preprocessor-directives.md)
