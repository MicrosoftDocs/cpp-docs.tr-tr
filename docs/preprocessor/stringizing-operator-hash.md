---
title: Dizeleyen işleç (#)
ms.date: 08/29/2019
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
ms.openlocfilehash: 5a1b43198e59bc1e69cdf1b56db56be75719fe46
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/03/2019
ms.locfileid: "70216543"
---
# <a name="stringizing-operator-"></a>Dizeleyen işleç (#)

Sayı işareti veya "stringize" işleci ( **#** ), parametre tanımını genişletmeksizin makro parametrelerini dize sabit değerlerine dönüştürür. Yalnızca bağımsız değişken alan makrolarla kullanılır. Makro tanımında biçimsel bir parametreden önce gelirse, makro çağrısı tarafından geçirilen gerçek bağımsız değişken tırnak işaretleri içine alınır ve dize sabit değeri olarak değerlendirilir. Daha sonra dize sabit değeri, dize haline getirme işleci ile biçimsel parametrenin makro tanımındaki her birleşim örneğini değiştirir.

> [!NOTE]
> ANSI C standardının önceden dize sabit değerleri ve karakter sabitleri içinde görünen makro biçimsel bağımsız değişkenlerini genişleten Microsoft C (6.0 ve önceki sürümleri) uzantısı, artık desteklenmemektedir. Bu uzantıya bağlı olan kodun stringize ( **#** ) işleci kullanılarak yeniden yazılması gerekir.

İlk belirteçten önce gelen ve gerçek bağımsız değişkenin son belirtecini izleyen boşluk yok sayılır. Gerçek bağımsız değişkendeki belirteçler arasında yer alan boşluklar, ortaya çıkan dize sabit değerinde tek bir boşluk olarak azaltılır. Bu nedenle, gerçek bağımsız değişkende iki belirteç arasında bir yorum oluşursa, tek bir boşluk olarak azaltılır. Elde edilen dize değişmez değeri, yalnızca boşluk ile ayrılmış olan bitişik dize değişmez değerleri ile otomatik olarak birleştirilir.

Ayrıca, bağımsız değişkende bulunan bir karakter genellikle bir dize sabit değerinde kullanıldığında bir kaçış sırası gerektiriyorsa (örneğin, tırnak işareti (`"`) veya ters eğik çizgi (`\`) karakteri), gerekli kaçış ters eğik çizgi otomatik olarak karakterden önce eklenirler.

Microsoft C++ stringize işleci, kaçış dizileri içeren dizeler ile kullanıldığında doğru şekilde davranmaz. Bu durumda, derleyici [derleyici hatası C2017](../error-messages/compiler-errors-1/compiler-error-c2017.md)oluşturur.

## <a name="examples"></a>Örnekler

Aşağıdaki örnek, stringize işleci ve makroyu çağıran bir ana işlev içeren bir makro tanımı gösterir:

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

`stringer` Makrolar ön işleme sırasında genişletilir ve aşağıdaki kod oluşturulur:

```cpp
int main() {
   printf_s( "In quotes in the printf function call" "\n" );
   printf_s( "\"In quotes when printed to the screen\"" "\n" );
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

[Önişlemci işleçleri](../preprocessor/preprocessor-operators.md)
