---
title: "Ek işleçler: + ve - | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- +
- '-'
dev_langs: C++
helpviewer_keywords:
- operators [C++], addition
- subtraction operator [C++], additive operators
- + operator [C++], additive operators
- additive operators [C++]
- arithmetic operators [C++], additive operators
- '- operator [C++], additive operators in C++'
ms.assetid: d4afafe7-e201-4c69-a649-37f17756e784
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 02909b9b42ca781f7a178aa4b9dc7440bd89f2a7
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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
  
 Toplama işleçleri aritmetik veya işaretçi türlerinin işlenen alır. Toplamın sonucunu (**+**) işleci işlenenler toplamıdır. Çıkarma sonucu (**-**) işlecidir işlenenleri arasındaki fark. Bir veya iki işlenen işaretçileri varsa, işaretçileri nesnelere değil, işlevleri olmaları gerekir. Her iki işlenen işaretçileri olursa, her ikisi de aynı dizide nesnelerine işaretçiler olmadıkça sonuçları anlamlı değildir.  
  
 Toplama işleçleri ele işlenenleri *aritmetik*, *tam sayı*, ve *skaler* türleri. Bunlar aşağıdaki tabloda tanımlanır.  
  
### <a name="types-used-with-additive-operators"></a>Toplama işleçleri ile kullanılan türleri  
  
|Tür|Açıklama|  
|----------|-------------|  
|*aritmetik*|Kayan ve tam sayı türleri topluca "aritmetik" türleri olarak adlandırılır.|  
|*tam sayı*|Türleri char ve tüm boyutları (uzun ve kısa) ve numaralandırmalar int "tümleşik" türleridir.|  
|*skaler*|Skaler işleçler aritmetik veya işaretçi türündeki işlenenler ' dir.|  
  
 Bu işleçlere yasal birleşimleridir:  
  
 *aritmetik* + *aritmetik*  
  
 *skaler* + *tam sayı*  
  
 *tam sayı* + *skaler*  
  
 *aritmetik* - *aritmetik*  
  
 *skaler* - *skaler*  
  
 Toplama ve çıkarma eşdeğer işlemleri olmadığına dikkat edin.  
  
 Her iki işlenen aritmetik türdeyse, dönüştürmeleri ele [standart dönüşümler](standard-conversions.md) işlenenler için uygulanır ve sonuç dönüştürülen türüdür.  
  
## <a name="example"></a>Örnek  
  
```  
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
  
## <a name="pointer-addition"></a>İşaretçi ekleme  
 Ek bir işlem içinde, işlenenlerden biri nesneleri içeren bir dizinin işaretçisi ise, diğeri tamsayı türünde olmalıdır. Sonuç, özgün işaretçi ile aynı türde ve başka bir dizi öğesine işaret eden bir işaretçidir. Aşağıdaki kod parçası bu kavramı gösterir:  
  
```  
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
 Her iki işlenen de işaretçiyse, çıkarma işleminin sonucu işlenenler arasındaki farktır (dizi öğelerinde). Çıkarma ifadesi, ptrdiff_t (STDDEF.H standart içerme dosyasında tanımlanır) türünün işaretli integral sonucunu verir.  
  
 İşlenenlerden biri, ikinci işlenen olduğu takdirde integral türünde olabilir. Çıkarma işleminin sonucu, orijinal işaretçiyle aynı türdendir. Çıkarma değerini gösteren bir işaretçidir (*n* - *ı*) th dizi öğesi, burada  *n*  öğesi işaret ediyor özgün işaretçi ve *ı* ikinci işlenen tam sayı değeri.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İkili işleçli ifadeler](../cpp/expressions-with-binary-operators.md)   
 [C++ yerleşik işleçleri, öncelik ve birleşim](../cpp/cpp-built-in-operators-precedence-and-associativity.md)   
 [C ek işleçleri](../c-language/c-additive-operators.md)
