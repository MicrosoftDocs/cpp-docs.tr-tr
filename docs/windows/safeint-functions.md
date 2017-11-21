---
title: "SafeInt işlevleri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
helpviewer_keywords: functions, SafeInt
ms.assetid: fdc208e5-5d8a-41a9-8271-567fd438958d
caps.latest.revision: "13"
author: ghogen
ms.author: ghogen
manager: ghogen
ms.openlocfilehash: 7b71ee1088c60ea1c13b04fef517169f40a32d96
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="safeint-functions"></a>SafeInt İşlevleri
SafeInt Kitaplığı örneğini oluşturmadan kullanabileceğiniz birçok işlevleri sağlar [SafeInt sınıfı](../windows/safeint-class.md). Tek bir matematik işlemi tamsayı Taşma alanındaki korumak istiyorsanız, bu işlevler kullanabilirsiniz. Birden çok matematik işlemleri korumak istiyorsanız, oluşturmalısınız `SafeInt` nesneleri. Oluşturmak için daha verimlidir `SafeInt` birden çok kez bu işlevler kullanımı çok nesneleri.  
  
 Bu işlevler karşılaştırmak veya ilk aynı türüne dönüştürmek zorunda kalmadan parametreleri iki farklı türde matematik işlemleri gerçekleştirmenize imkan sağlar.  
  
 Bu işlevlerin her iki şablon türü vardır: `T` ve `U`. Bu türlerinin her biri bir Boole değeri, karakter ya da tam sayı türü olabilir. Tam sayı türleri imzalı veya imzasız ve herhangi bir boyuta 8 bitten 64 bit.  
  
## <a name="in-this-section"></a>Bu Bölümde  
  
|İşlev|Açıklama|  
|--------------|-----------------|  
|[SafeAdd](../windows/safeadd.md)|İki sayı ekleyen ve taşma karşı korur.|  
|[SafeCast](../windows/safecast.md)|Başka bir tür parametresi bir tür çevirir.|  
|[SafeDivide](../windows/safedivide.md)|İki sayıyı böler ve sıfıra bölme karşı korur.|  
|[SafeEquals](../windows/safeequals.md), [SafeGreaterThan](../windows/safegreaterthan.md), [SafeGreaterThanEquals](../windows/safegreaterthanequals.md), [SafeLessThan](../windows/safelessthan.md), [SafeLessThanEquals](../windows/safelessthanequals.md), [SafeNotEquals](../windows/safenotequals.md)|İki sayı karşılaştırır. Bu işlevler türlerini değiştirmeden numaraları iki farklı türde karşılaştırmanıza olanak sağlar.|  
|[SafeModulus](../windows/safemodulus.md)|İki sayı üzerinde modulus işlemi gerçekleştirir.|  
|[SafeMultiply](../windows/safemultiply.md)|İki sayı birlikte çarpar ve taşma karşı korur.|  
|[SafeSubtract](../windows/safesubtract.md)|İki sayı çıkarır ve taşma karşı korur.|  
  
## <a name="related-sections"></a>İlgili Bölümler  
  
|Bölüm|Açıklama|  
|-------------|-----------------|  
|[SafeInt sınıfı](../windows/safeint-class.md)|`SafeInt` Sınıfı.|  
|[Safeıntexception sınıfı](../windows/safeintexception-class.md)|SafeInt Kitaplığı'na belirli özel durum sınıfı.|