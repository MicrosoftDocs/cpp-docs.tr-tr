---
title: "Dizeleyen işleç (#) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: '#'
dev_langs: C++
helpviewer_keywords:
- preprocessor, operators
- arguments [C++], converting to strings
- stringizing operator
- preprocessor
- string literals, converting macro parameters to
- macros [C++], converting parameters to strings
- '# preprocessor operator'
ms.assetid: 1175dd19-4538-43b3-ad97-a008ab80e7b1
caps.latest.revision: "16"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 585bdd0fa11cecdf3fb337f8c11d2287fe495371
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="stringizing-operator-"></a>Dizeleyen İşleç (#)
Sayı işareti ya da "dizeleyen" işleci (**#**) dönüştürür makrosu parametreleri dize değişmez değerleri parametre tanımına genişletmeden. Yalnızca bağımsız değişkenler alan makrolarla kullanılır. Makro tanımında biçimsel bir parametreden önce gelirse, makro çağrısı tarafından geçirilen gerçek bağımsız değişken tırnak işaretleri içine alınır ve dize sabit değeri olarak değerlendirilir. Daha sonra dize sabit değeri, dize haline getirme işleci ile biçimsel parametrenin makro tanımındaki her birleşim örneğini değiştirir.  
  
> [!NOTE]
>  ANSI C standardının önceden dize sabit değerleri ve karakter sabitleri içinde görünen makro biçimsel bağımsız değişkenlerini genişleten Microsoft C (6.0 ve önceki sürümleri) uzantısı, artık desteklenmemektedir. Bu uzantı dayanıyordu kod yeniden yazılmıştır dizeleyen kullanarak (**#**) işleci.  
  
Gerçek bağımsız değişkenin ilk belirtecinden önce ve son belirtecinden sonra gelen boşluk yoksayılır. Gerçek bağımsız değişkendeki belirteçler arasında yer alan boşluklar, ortaya çıkan dize sabit değerinde tek bir boşluk olarak azaltılır. Bu nedenle, gerçek bağımsız değişkendeki iki belirteç arasında bir açıklama ortaya çıkarsa, tek bir boşluk olarak azaltılır. Ortaya çıkan dize sabit değeri, otomatik olarak yalnızca boşlukla ayrıldığı bitişik sabit dize değeriyle birleştirilir.  
  
Bir dize sabit değeri kullanıldığında bir kaçış sırası değişkeninde genellikle bulunan bir karakter gerektiriyorsa, daha fazla (örneğin, tırnak işareti (**"**) veya ters eğik çizgi (**\\**) karakter), gerekli kaçış ters eğik çizgi karakteri önce otomatik olarak eklenir.  
  
Kaçış dizileri içeren dizelerle kullanıldığında Visual C++ stringizing işleci düzgün çalışmasını değil. Bu durumda, derleyici oluşturur [derleyici hatası C2017](../error-messages/compiler-errors-1/compiler-error-c2017.md).  
  
## <a name="example"></a>Örnek  
Aşağıdaki örnekte, dize haline getirme işlecini ve makroyu çağıran ana işlevi içeren bir makro tanımı gösterilmektedir:  
  
Böyle çağrılar ön işlem sırasında genişletilerek aşağıdaki kod oluşturulur:  
  
```cpp  
int main() {  
   printf_s( "In quotes in the printf function call\n" "\n" );  
   printf_s( "\"In quotes when printed to the screen\"\n" "\n" );  
   printf_s( "\"This: \\\" prints an escaped double quote\"" "\n" );  
}  
```  
  
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
  
```Output  
In quotes in the printf function call  
"In quotes when printed to the screen"  
"This: \"  prints an escaped double quote"  
```  
  
## <a name="example"></a>Örnek  
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
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Ön İşlemci işleçleri](../preprocessor/preprocessor-operators.md)