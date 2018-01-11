---
title: "Bildirimler ve değişken bildirimleri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- declaring variables, declarators
- declarators, definition
- declaring variables, declaration statements
ms.assetid: 5fd67a6a-3a6a-4ec9-b257-3f7390a48d40
caps.latest.revision: "13"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 2d9b7ce4895d51c50185c5262664dc478af62cfa
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="declarators-and-variable-declarations"></a>Bildirimler ve Değişken Bildirimleri
Bu bölümde rest form ve bu listede özetlenen değişken türleri için bildirimleri anlamını açıklar. Özellikle, kalan bölümleri aşağıdaki bildirme açıklamaktadır:  
  
|Değişken türü|Açıklama|  
|----------------------|-----------------|  
|[Basit değişkenler](../c-language/simple-variable-declarations.md)|Tam sayı veya kayan nokta türüyle tek değerli değişkenleri|  
|[Diziler](../c-language/array-declarations.md)|Aynı türde öğe koleksiyonunu oluşan değişkenleri|  
|[İşaretçiler](../c-language/pointer-declarations.md)|Diğer değişkenlere işaret eden ve değerleri yerine (adresleri biçiminde) değişken konumlarını içeren değişkenleri|  
|[Numaralandırma değişkenleri](../c-language/c-enumeration-declarations.md)|İntegral basit değişkenlerle adlandırılmış tamsayı sabitleri kümesinden bu tutun bir değer yazın|  
|[Yapılar](../c-language/structure-declarations.md)|Farklı türe sahip değerleri koleksiyonunu oluşan değişkenleri|  
|[Birleşimler](../c-language/union-declarations.md)|Aynı depolama alanı kaplar farklı türlerde birkaç değerlerinden oluşan değişkenleri|  
  
 Bir bildirimcisi programa sunulması adını belirten bir bildirim parçasıdır. Değiştiriciler gibi içerebilir  **\***  (işaretçi-için) ve Microsoft çağırma kuralı anahtar sözcükler.  
  
 **Microsoft özel**  
  
 Bildirimcisi  
  
```  
__declspec(thread) char *var;  
```  
  
 `char`tür belirleyici olduğu `__declspec(thread)` ve `*` değiştiricileri olan ve `var` Identifier'ın adı.  
  
 **SON Microsoft özel**  
  
 Değer, değerleri ve belirtilen bir türün değerler döndüren işlev işaretçileri dizileri bildirmek için Bildirimciler kullanın. Bildirimleri daha sonra bu bölümde açıklanan dizi ve işaretçi bildirimleri görünür.  
  
## <a name="syntax"></a>Sözdizimi  
 *bildirimcisi*:  
 &nbsp;&nbsp;*İşaretçi*<sub>kabul</sub> *doğrudan bildirimcisi*  
  
 *doğrudan bildirimcisi*:  
 &nbsp;&nbsp;*tanımlayıcı*  
 &nbsp;&nbsp;**(***bildirimcisi***)**   
 &nbsp;&nbsp;*doğrudan bildirimcisi***[***sabit ifadesi*<sub>kabul</sub> **]**   
 &nbsp;&nbsp;*doğrudan bildirimcisi***(***parametre türü listesi***)**   
 &nbsp;&nbsp;*doğrudan bildirimcisi***(***tanımlayıcı listesi*<sub>kabul</sub> **)**   
  
 *İşaretçi*:  
 &nbsp;&nbsp;**\****tür niteleyicisi listesi*<sub>iptal et</sub>  
 &nbsp;&nbsp;**\****tür niteleyicisi listesi*<sub>kabul</sub> *işaretçi*  
  
 *tür niteleyicisi listesi*:  
 &nbsp;&nbsp;*tür niteleyicisi*  
 &nbsp;&nbsp;*tür niteleyicisi listesi tür niteleyicisi*  
  
> [!NOTE]
>  Sözdizimi için bkz *bildirimi* içinde [genel bakış, bildirimler](../c-language/overview-of-declarations.md) veya [C dili sözdizimi özeti](../c-language/c-language-syntax-summary.md) başvuruda bulunan bir sözdizimi için bir *bildirimcisi*.  
  
 Bir bildirimcisi değiştirilmemiş tanıtıcısı oluşuyorsa bildirilen öğesi bir temel türe sahip. Yıldız işareti (**\***) türü için bir işaretçi türü değiştiren bir tanımlayıcı solunda görünür. Tanımlayıcı köşeli parantez izlediyseniz (**[]**), türü için bir dizi türü değiştirilir. Tanımlayıcısı tarafından parantez izlediyseniz türü bir işlev türü değiştirildi. Öncelik bildirimleri içinde yorumlama hakkında daha fazla bilgi için bkz: [daha fazla karmaşık Bildirimcileri yorumlama](../c-language/interpreting-more-complex-declarators.md).  
  
 Her bildirimcisi en az bir tanımlayıcı bildirir. Bir bildirimcisi tam bildirimi olması için bir tür belirteci eklemeniz gerekir. Tür belirleyici bir dizi türü, bir işaretçi türü tarafından ele nesne türünü veya bir işlevin dönüş türü öğelerin türü sağlar.  
  
 [Dizi](../c-language/array-declarations.md) ve [işaretçi](../c-language/pointer-declarations.md) bildirimleri, bu bölümde ileride daha ayrıntılı açıklanmıştır. Aşağıdaki örneklerde bildiricilere birkaç basit form gösterilmektedir:  
  
```  
int list[20]; // Declares an array of 20 int values named list  
char *cp;     // Declares a pointer to a char value  
double func( void ); // Declares a function named func, with no   
                     // arguments, that returns a double value  
int *aptr[10] // Declares an array of 10 pointers  
```  
  
 **Microsoft özel**  
  
 Microsoft C Derleyici bir aritmetik, yapı ve birleşim türü değiştirebilirsiniz Bildirimciler sayısını sınırlamaz. Kullanılabilir bellek tarafından sınırlıdır.  
  
 **SON Microsoft özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bildirimler ve Türler](../c-language/declarations-and-types.md)