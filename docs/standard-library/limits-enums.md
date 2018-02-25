---
title: "&lt;sınırları&gt; numaralandırmaları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- limits/std::float_denorm_style
- limits/std::float_round_style
ms.assetid: c86680a2-ba97-4ed9-8c20-a448857d7dc5
caps.latest.revision: 
manager: ghogen
ms.openlocfilehash: a776ccd0299c3acc43763a381ce337c67bc6c134
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/23/2018
---
# <a name="ltlimitsgt-enums"></a>&lt;sınırları&gt; numaralandırmaları
|||  
|-|-|  
|[float_denorm_style](#float_denorm_style)|[float_round_style](#float_round_style)|  
  
##  <a name="float_denorm_style"></a>  float_denorm_style numaralandırması  
 Numaralandırma Normalleştirilmemiş kayan noktalı bir sayıyı temsil eden bir uygulama seçebileceğiniz çeşitli yöntemlerini açıklar — normalleştirilmiş değeri olarak göstermek için çok küçük bir:  
  
```
enum float_denorm_style {
    denorm_indeterminate = -1,
    denorm_absent = 0,
    denorm_present = 1    };
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Numaralandırması döndürür:  
  
- **denorm_indeterminate** varlığının veya yokluğunun Normalleştirilmemiş formların çeviri zaman belirlenemiyorsa.  
  
- **denorm_absent** Normalleştirilmemiş forms yoksa.  
  
- **denorm_present** Normalleştirilmemiş forms varsa.  
  
### <a name="example"></a>Örnek  
  Bkz: [numeric_limits::has_denorm](../standard-library/numeric-limits-class.md#has_denorm) içinde bu numaralandırma değerlerini erişilebilir bir örnek.  
  
##  <a name="float_round_style"></a>  float_round_style numaralandırması  
 Numaralandırma bir tamsayı değeri kayan noktalı bir sayıyı yuvarlama uygulaması seçebileceğiniz çeşitli yöntemleri açıklar.  
  
```
enum float_round_style {    
    round_indeterminate = -1,
    round_toward_zero = 0,
    round_to_nearest = 1,
    round_toward_infinity = 2,
    round_toward_neg_infinity = 3    };
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Numaralandırması döndürür:  
  
- **round_indeterminate** yuvarlama yöntemi belirlenemiyorsa.  
  
- **round_toward_zero** , sıfıra doğru YUVARLA.  
  
- **round_to_nearest** , en yakın tamsayıya yuvarlamak.  
  
- **round_toward_infinity** varsa gidiş uzağa doğru yuvarlar.  
  
- **round_toward_neg_infinity** varsa daha negatif tamsayı değerine YUVARLA.  
  
### <a name="example"></a>Örnek  
  Bkz: [numeric_limits::round_style](../standard-library/numeric-limits-class.md#round_style) içinde bu numaralandırma değerlerini erişilebilir bir örnek.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [\<sınırları >](../standard-library/limits.md)



