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
ms.openlocfilehash: b8a0475b5d3ba9053cd5d2df5ffd99ce9292ba8e
ms.sourcegitcommit: 4586bfc32d8bc37ab08b24816d7fad5df709bfa3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/07/2018
ms.locfileid: "39603461"
---
# <a name="safeint-functions"></a>SafeInt İşlevleri
SafeInt Kitaplığı örneği oluşturulmadan kullanabileceğiniz çeşitli işlevler sağlar [SafeInt sınıfı](../windows/safeint-class.md). Tek bir matematiksel işlem tamsayı taşmasından korumak istiyorsanız, bu işlevleri kullanabilirsiniz. Birden çok matematik işlemi korumak istiyorsanız, oluşturmalısınız **SafeInt** nesneleri. Oluşturmak için daha verimlidir **SafeInt** birden çok kez bu işlevlerin kullanımı çok nesneleri.  
  
 Bu işlevler karşılaştırmak ya da önce aynı türe dönüştürmek zorunda kalmadan iki farklı türde parametreler matematik işlemlerini gerçekleştirmek etkinleştirin.  
  
 Bu işlevlerin her biri iki şablon türü vardır: `T` ve `U`. Bu türlerinin her biri bir Boole değeri, karakter veya bir tamsayı türü olabilir. Tam sayı türleri imzalı veya imzasız tüm boyutlardaki 8 bitten 64 bite.  
  
## <a name="in-this-section"></a>Bu Bölümde  
  
|İşlev|Açıklama|  
|--------------|-----------------|  
|[SafeAdd](../windows/safeadd.md)|İki sayı ekleyen ve taşmasına karşı korur.|  
|[SafeCast](../windows/safecast.md)|Başka bir tür parametresine bir tür çevirir.|  
|[SafeDivide](../windows/safedivide.md)|İki sayıyı böler ve sıfıra bölme karşı korur.|  
|[SafeEquals](../windows/safeequals.md), [SafeGreaterThan](../windows/safegreaterthan.md), [SafeGreaterThanEquals](../windows/safegreaterthanequals.md), [SafeLessThan](../windows/safelessthan.md), [SafeLessThanEquals](../windows/safelessthanequals.md), [ SafeNotEquals](../windows/safenotequals.md)|İki sayıyı karşılaştırır. Bu işlevler, iki farklı tür sayı türlerini değiştirmeden karşılaştırmanızı sağlar.|  
|[SafeModulus](../windows/safemodulus.md)|İki sayıyı mod işlemi gerçekleştirir.|  
|[SafeMultiply](../windows/safemultiply.md)|Birlikte iki sayıyı çarpar ve taşmasına karşı korur.|  
|[SafeSubtract](../windows/safesubtract.md)|İki sayıyı çıkarır ve taşmasına karşı korur.|  
  
## <a name="related-sections"></a>İlgili Bölümler  
  
|Bölüm|Açıklama|  
|-------------|-----------------|  
|[SafeInt Sınıfı](../windows/safeint-class.md)|**SafeInt** sınıfı.|  
|[SafeIntException Sınıfı](../windows/safeintexception-class.md)|SafeInt Kitaplığı'na belirli özel durum sınıfı.|