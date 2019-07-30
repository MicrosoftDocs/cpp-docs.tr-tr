---
title: Dizeleyen İşleç (#)
ms.date: 11/04/2016
f1_keywords:
- '#'
helpviewer_keywords:
- preprocessor, operators
- arguments [C++], converting to strings
- stringizing operator
- preprocessor
- string literals, converting macro parameters to
- macros [C++], converting parameters to strings
- '# preprocessor operator'
ms.assetid: 1175dd19-4538-43b3-ad97-a008ab80e7b1
ms.openlocfilehash: 720817b34326d822ef797351655e4ace907e4baf
ms.sourcegitcommit: 20a1356193fbe0ddd1002e798b952917eafc3439
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/30/2019
ms.locfileid: "68661621"
---
# <a name="stringizing-operator-"></a>Dizeleyen İşleç (#)

Sayı işareti veya "stringize" işleci ( **#** ), parametre tanımını genişletmeksizin makro parametrelerini dize sabit değerlerine dönüştürür. Yalnızca bağımsız değişkenler alan makrolarla kullanılır. Makro tanımında biçimsel bir parametreden önce gelirse, makro çağrısı tarafından geçirilen gerçek bağımsız değişken tırnak işaretleri içine alınır ve dize sabit değeri olarak değerlendirilir. Daha sonra dize sabit değeri, dize haline getirme işleci ile biçimsel parametrenin makro tanımındaki her birleşim örneğini değiştirir.

> [!NOTE]
> ANSI C standardının önceden dize sabit değerleri ve karakter sabitleri içinde görünen makro biçimsel bağımsız değişkenlerini genişleten Microsoft C (6.0 ve önceki sürümleri) uzantısı, artık desteklenmemektedir. Bu uzantıya bağlı olan kodun stringize ( **#** ) işleci kullanılarak yeniden yazılması gerekir.

Gerçek bağımsız değişkenin ilk belirtecinden önce ve son belirtecinden sonra gelen boşluk yoksayılır. Gerçek bağımsız değişkendeki belirteçler arasında yer alan boşluklar, ortaya çıkan dize sabit değerinde tek bir boşluk olarak azaltılır. Bu nedenle, gerçek bağımsız değişkendeki iki belirteç arasında bir açıklama ortaya çıkarsa, tek bir boşluk olarak azaltılır. Ortaya çıkan dize sabit değeri, otomatik olarak yalnızca boşlukla ayrıldığı bitişik sabit dize değeriyle birleştirilir.

Ayrıca, bağımsız değişkende bulunan bir karakter genellikle bir dize sabit değerinde kullanıldığında (örneğin, tırnak işareti ( **"** ) veya ters eğik çizgi ( **\\** ) karakteri) bir kaçış sırası gerektiriyorsa, gerekli kaçış ters eğik çizgi otomatik olarak eklenir karakterden önce.

Kaçış dizileri C++ içeren dizeler Ile kullanıldığında görsel stringize işleci doğru davranmaz. Bu durumda, derleyici [derleyici hatası C2017](../error-messages/compiler-errors-1/compiler-error-c2017.md)oluşturur.

## <a name="examples"></a>Örnekler

Aşağıdaki örnekte, dize haline getirme işlecini ve makroyu çağıran ana işlevi içeren bir makro tanımı gösterilmektedir:

```cpp
// stringizer.cpp
#include <stdio.h>
#define stringer( x ) printf_s( #x "\n" )
int main() {
   stringer( In quotes in the printf function call );
   stringer( "In quotes when printed to the screen" );
   stringer( "This: \"  prints an escaped double quote" );
}
```

Böyle çağrılar ön işlem sırasında genişletilerek aşağıdaki kod oluşturulur:

```cpp
int main() {
   printf_s( "In quotes in the printf function call\n" "\n" );
   printf_s( "\"In quotes when printed to the screen\"\n" "\n" );
   printf_s( "\"This: \\\" prints an escaped double quote\"" "\n" );
}
```

```Output
In quotes in the printf function call
"In quotes when printed to the screen"
"This: \"  prints an escaped double quote"
```

Aşağıdaki örnekte, bir makro parametresini nasıl genişletebileceğiniz gösterilmektedir:

```cpp
// stringizer_2.cpp
// compile with: /E
#define F abc
#define B def
#define FB(arg) #arg
#define FB1(arg) FB(arg)
FB(F B)
FB1(F B)
```

## <a name="see-also"></a>Ayrıca bkz.

[Ön İşlemci İşleçleri](../preprocessor/preprocessor-operators.md)
