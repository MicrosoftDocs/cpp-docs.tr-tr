---
title: SafeInt işlevleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- functions, SafeInt
ms.assetid: fdc208e5-5d8a-41a9-8271-567fd438958d
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 97edd25abca3c9e80a35745165eedc93cc13a9b9
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33889313"
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
|[SafeEquals](../windows/safeequals.md), [SafeGreaterThan](../windows/safegreaterthan.md), [SafeGreaterThanEquals](../windows/safegreaterthanequals.md), [SafeLessThan](../windows/safelessthan.md), [SafeLessThanEquals](../windows/safelessthanequals.md), [ SafeNotEquals](../windows/safenotequals.md)|İki sayı karşılaştırır. Bu işlevler türlerini değiştirmeden numaraları iki farklı türde karşılaştırmanıza olanak sağlar.|  
|[SafeModulus](../windows/safemodulus.md)|İki sayı üzerinde modulus işlemi gerçekleştirir.|  
|[SafeMultiply](../windows/safemultiply.md)|İki sayı birlikte çarpar ve taşma karşı korur.|  
|[SafeSubtract](../windows/safesubtract.md)|İki sayı çıkarır ve taşma karşı korur.|  
  
## <a name="related-sections"></a>İlgili Bölümler  
  
|Bölüm|Açıklama|  
|-------------|-----------------|  
|[SafeInt Sınıfı](../windows/safeint-class.md)|`SafeInt` Sınıfı.|  
|[SafeIntException Sınıfı](../windows/safeintexception-class.md)|SafeInt Kitaplığı'na belirli özel durum sınıfı.|