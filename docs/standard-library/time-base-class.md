---
title: "time_base sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- locale/std::time_base
dev_langs:
- C++
helpviewer_keywords:
- time_base class
ms.assetid: 9ae37f0b-9a42-496e-9870-3d9b71bab8fb
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: cc7ed644d7c66ea7e3ca49b6d403b17535fa3eb9
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/23/2018
---
# <a name="timebase-class"></a>time_base Sınıfı
Sınıf şablonu sınıfı time_get yalnızca numaralandırılmış türünü tanımlamak, modelleri için temel bir sınıf olarak hizmet veren **dateorder** ve bu tür birkaç sabitleri.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
class time_base : public locale::facet {
public:
    enum dateorder {no_order,
    dmy,
 mdy,
    ymd,
 ydm};
    time_base(
 size_t _Refs = 0)
 ~time_base();

};
```  
  
## <a name="remarks"></a>Açıklamalar  
 Her sabit bir tarih bileşenlerinin sıralamak için farklı bir şekilde belirtir. Sabitler şunlardır:  
  
- **no_order** belirli bir sırada belirtir.  
  
- **GAY** sipariş gün, ay ve yıl, 2 aralık 1979 olduğu gibi belirtir.  
  
- **AGY** sipariş ay, gün sonra 2 aralık 1979 olduğu gibi yıl belirtir.  
  
- **YAG'dir** sipariş yıl, ay, ardından 1979/12/2 gibi gün belirtir.  
  
- **ydm** sipariş yıl, gün, ay, 1979:2 Ara olduğu gibi belirtir.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<yerel ayar >  
  
 **Namespace:** std  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)



