---
title: "duration_values yapısı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- chrono/std::chrono::duration_values
- chrono/std::chrono::duration_values::max
- chrono/std::chrono::duration_values::min
- chrono/std::chrono::duration_values::zero
dev_langs: C++
ms.assetid: 7f66d2e3-1faf-47c3-b47e-08f2a87f20e8
caps.latest.revision: "13"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 52c88e0b536eba6265e2f968adef8096ea4ab17e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="durationvalues-structure"></a>duration_values Yapısı
Belirli değerleri sağlar [süresi](../standard-library/duration-class.md) şablon parametresi `Rep`.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
template <class Rep>  
struct duration_values;  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[max](#max)|Statik. Türünde bir değer üst sınırını belirtir `Rep`.|  
|[Min](#min)|Statik. Türünde bir değer alt sınırı belirtir `Rep`.|  
|[sıfır](#zero)|Statik. Döndürür `Rep(0)`.|  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<chrono >  
  
 **Namespace:** std::chrono  
  
##  <a name="max"></a>duration_values::Max  
 Türü değerleri için üst sınır döndüren statik yöntem `Ref`.  
  
```  
static constexpr Rep max();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Uygulamada döndürür `numeric_limits<Rep>::max()`.  
  
### <a name="remarks"></a>Açıklamalar  
 Zaman `Rep` bir kullanıcı tanımlı tür dönüş değeri büyük olmalı [duration_values::zero](#zero).  
  
##  <a name="min"></a>duration_values::Min  
 Alt sınır türü değerleri için döndüren statik yöntem `Ref`.  
  
```  
static constexpr Rep min();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Uygulamada döndürür `numeric_limits<Rep>::lowest()`.  
  
### <a name="remarks"></a>Açıklamalar  
 Zaman `Rep` bir kullanıcı tanımlı tür dönüş değeri küçük veya eşit olmalıdır [duration_values::zero](#zero).  
  
##  <a name="zero"></a>duration_values::Zero  
 Döndürür `Rep(0)`.  
  
```  
static constexpr Rep zero();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Zaman `Rep` bir kullanıcı tanımlı tür eklenebilir sonsuz dönüş değerini temsil etmelidir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Üstbilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)   
 [\<chrono >](../standard-library/chrono.md)

