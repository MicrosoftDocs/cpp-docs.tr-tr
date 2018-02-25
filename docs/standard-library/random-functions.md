---
title: "&lt;rastgele&gt; işlevleri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- random/std::generate_canonical
ms.assetid: 2ac9ec59-619b-4b85-a425-f729277c1bc8
helpviewer_keywords:
- std::generate_canonical
caps.latest.revision: 
manager: ghogen
ms.openlocfilehash: 4833ef603341c7beb65cc31697a8ac5a62e15053
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/23/2018
---
# <a name="ltrandomgt-functions"></a>&lt;rastgele&gt; işlevleri
  
##  <a name="generate_canonical"></a>  generate_canonical  
 Kayan nokta değeri rastgele bir dizisini döndürür.  
  
> [!NOTE]
>  Bu işlev aralığındaki değerler döndürmesi gerektiğini ISO C++ Standart durumları [ `0`, `1`). Visual Studio henüz bu kısıtlaması ile uyumlu değil. Bu aralıkta değerlerini oluşturmak için geçici bir çözüm olarak kullanmak [uniform_real_distribution](../standard-library/uniform-real-distribution-class.md).  
  
```  
template <class RealType, size_t Bits, class Generator>  
RealType generate_canonical(Generator& Gen);
```  
  
### <a name="parameters"></a>Parametreler  
 `RealType`  
 Kayan nokta tamsayı türü. Olası türleri için bkz: [ \<rastgele >](../standard-library/random.md).  
  
 `Bits`  
 Rastgele sayı üreticisinin.  
  
 `Gen`  
 Rastgele sayı üreticisinin.  
  
### <a name="remarks"></a>Açıklamalar  
 Şablon işlev çağrılarını `operator()` , `Gen` art arda ve kayan noktalı bir sayıyı döndürülen değerlerin paketleri `x` türü `RealType` Mantis bit cinsinden belirtilen sayıda topladı kadar `x`. Belirtilen sayı olan küçük `Bits` (hangi olmalıdır sıfır olmayan) ve Mantis bit tam sayı `RealType`. İlk çağrıda en düşük sıra bitleri sağlar. İşlevi döndürür `x`.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [\<rastgele >](../standard-library/random.md)

