---
title: 'Ek işleçler: + ve - | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- +
- '-'
dev_langs:
- C++
helpviewer_keywords:
- operators [C++], addition
- subtraction operator [C++], additive operators
- + operator [C++], additive operators
- additive operators [C++]
- arithmetic operators [C++], additive operators
- '- operator [C++], additive operators in C++'
ms.assetid: d4afafe7-e201-4c69-a649-37f17756e784
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 313e4602c06c1baf090ed7a66c51b308a3f6f586
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/01/2018
ms.locfileid: "39402756"
---
# <a name="additive-operators--and--"></a>Ek İşleçler: + and -
## <a name="syntax"></a>Sözdizimi  
  
```  
expression + expression   
expression - expression  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Ek işleçler şunlardır:  
  
-   Toplama (**+**)  
  
-   Çıkarma (**-**)  
  
 Bu ikili işleçlerde soldan sağa ilişkilendirilebilirlik vardır.  
  
 Ek işleçler işlenenlerin aritmetik veya işaretçi türü yararlanın. Toplamın sonucunu (**+**) işleci işlenenler toplamıdır. Çıkarma işleminin sonucu (**-**) işlecinin işlenenleri arasındaki fark olarak. Bir veya iki işlenen de işaretçiyse, nesneler için değil, işlev işaretçileri olmaları gerekir. Her iki işlenen de işaretçiyse, her ikisi de aynı dizide nesne işaretçileri olmadığı sürece sonuç anlamlı değildir.  
  
 Toplama işleçleri ele işleneni *aritmetik*, *integral*, ve *skaler* türleri. Bunlar aşağıdaki tabloda tanımlanır.  
  
### <a name="types-used-with-additive-operators"></a>Toplama işleçleri ile kullanılan türler  
  
|Tür|Açıklama|  
|----------|-------------|  
|*Aritmetik*|İntegral ve kayan türler topluca "aritmetik" türleri adı verilir.|  
|*tam sayı*|Tür char ve tüm boyutları (uzun, kısa) ve numaralandırmalar int "tümleşik" türleridir.|  
|*skaler*|Skaler işlenen, aritmetik veya işaretçi türünde işlenenler ' dir.|  
  
 Bu işleçler için yasal birleşimleridir:  
  
 *aritmetik* + *aritmetik*  
  
 *skaler* + *tamsayı*  
  
 *integral* + *skaler*  
  
 *aritmetik* - *aritmetik*  
  
 *skaler* - *skaler*  
  
 Toplama ve çıkarma eşdeğer operations olmadığına dikkat edin.  
  
 Her iki işlenen de aritmetik türde ise, içinde kapsanan dönüştürmeler [standart dönüştürmeler](standard-conversions.md) işlenenlere uygulanır ve sonuç dönüştürülmüş türü verir.  
  
## <a name="example"></a>Örnek  
  
```cpp 
// expre_Additive_Operators.cpp  
// compile with: /EHsc  
#include <iostream>  
#define SIZE 5  
using namespace std;  
int main() {  
   int i = 5, j = 10;  
   int n[SIZE] = { 0, 1, 2, 3, 4 };  
   cout  << "5 + 10 = " << i + j << endl  
         << "5 - 10 = " << i - j << endl;  
  
   // use pointer arithmetic on array  
  
   cout << "n[3] = " << *( n + 3 ) << endl;  
}  
```  
  
## <a name="pointer-addition"></a>İşaretçi toplama  
 Ek bir işlem içinde, işlenenlerden biri nesneleri içeren bir dizinin işaretçisi ise, diğeri tamsayı türünde olmalıdır. Sonuç, özgün işaretçi ile aynı türde ve başka bir dizi öğesine işaret eden bir işaretçidir. Aşağıdaki kod parçası bu kavramı gösterir:  
  
```cpp 
short IntArray[10]; // Objects of type short occupy 2 bytes  
short *pIntArray = IntArray;  
  
for( int i = 0; i < 10; ++i )  
{  
    *pIntArray = i;  
    cout << *pIntArray << "\n";  
    pIntArray = pIntArray + 1;  
}  
```  
  
 `pIntArray` öğesine tamsayı değeri olarak 1 eklenmiş olmasına rağmen, "adrese 1 ekle" anlamına gelmez; daha çok, "işaretçiyi dizideki sonraki nesneye işaret edecek şekilde ayarla" anlamına gelir, bu da 2 bayt (veya `sizeof( int )`) uzakta olur.  
  
> [!NOTE]
>  `pIntArray = pIntArray + 1` formunun kodu C++ programlarında nadiren bulunur; arttırma yapmak için şu formlar tercih edilir: `pIntArray++` veya `pIntArray += 1`.  
  
## <a name="pointer-subtraction"></a>İşaretçi çıkarması  
 Her iki işlenen de işaretçiyse, çıkarma işleminin sonucu işlenenler arasındaki farktır (dizi öğelerinde). Çıkarma ifadesi türü işaretli integral sonucunu verir `ptrdiff_t` (standart içerme dosyasında tanımlanan \<stddef.h >).  
  
 İşlenenlerden biri, ikinci işlenen olduğu takdirde integral türünde olabilir. Çıkarma işleminin sonucu, orijinal işaretçiyle aynı türdendir. Bir işaretçi çıkarma değeri (*n* - *miyim*) dizi öğesinin, burada *n* öğe için veorijinalişaretçitarafındanişaretedilen*miyim* ikinci işleneni integral değeridir.  
  
## <a name="see-also"></a>Ayrıca bkz.  
 [İkili işleçli ifadeler](../cpp/expressions-with-binary-operators.md)   
 [C++ yerleşik işleçler, öncelik ve İlişkisellik](../cpp/cpp-built-in-operators-precedence-and-associativity.md)   
 [C Ek İşleçleri](../c-language/c-additive-operators.md)