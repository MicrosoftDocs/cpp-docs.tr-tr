---
title: "independent_bits_engine sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: random/std::independent_bits_engine
dev_langs: C++
helpviewer_keywords: independent_bits_engine class
ms.assetid: 889e9a82-f457-49a7-9d2e-26e0fc3cd907
caps.latest.revision: "17"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 8ec9a4b9beac581df0060f239916c06b8b6191de
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="independentbitsengine-class"></a>independent_bits_engine Sınıfı
BITS repacking BITS tarafından belirtilen sayıda numaralarıyla rastgele bir dizi kendi temel altyapı tarafından döndürülen değer oluşturur.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
template <class Engine, size_t W, class UIntType>  
class independent_bits_engine;  
```  
  
### <a name="parameters"></a>Parametreler  
 `Engine`  
 Temel altyapısı türü.  
  
 `W`  
 **Word boyutu**. Oluşturulan her sayının bit cinsinden boyutu. **Önkoşul**:`0 < W ≤ numeric_limits<UIntType>::digits`  
  
 `UIntType`  
 İşaretsiz tamsayı sonuç türü. Olası türleri için bkz: [ \<rastgele >](../standard-library/random.md).  
  
## <a name="members"></a>Üyeler  
  
||||  
|-|-|-|  
|`independent_bits_engine::independent_bits_engine`|`independent_bits_engine::base`|`independent_bits_engine::discard`|  
|`independent_bits_engine::operator()`|`independent_bits_engine::base_type`|`independent_bits_engine::seed`|  
  
 Altyapısı üyeleri hakkında daha fazla bilgi için bkz: [ \<rastgele >](../standard-library/random.md).  
  
## <a name="remarks"></a>Açıklamalar  
 Bu şablon sınıf tanımlar bir *motoru bağdaştırıcı* , üreten değerleri bunun sonucunda, temel altyapısı tarafından döndürülen değerler bitten repacking tarafından `W`-bit değerleri.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<rastgele >  
  
 **Namespace:** std  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [\<rastgele >](../standard-library/random.md)

