---
title: "underlying_type sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: type_traits/std::underlying_type
dev_langs: C++
helpviewer_keywords: underlying_type
ms.assetid: 691ddce3-2677-4480-bd35-d933fab85d3e
caps.latest.revision: "13"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: b539f62e1e9c6b9bf11b176bd50f7dca63508ddd
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="underlyingtype-class"></a>underlying_type sınıfı
Bir numaralandırma türü için temel alınan tam sayı tür üretir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template <class T>  
struct underlying_type;
```  
  
#### <a name="parameters"></a>Parametreler  
 `T`  
 Değiştirilecek tür.  
  
## <a name="remarks"></a>Açıklamalar  
 `type` Şablon sınıfının üye typedef adları temel tam sayı türü `T`, `T` bir numaralandırma türü olan aksi hiçbir üye typedef yoktur `type`.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<type_traits >  
  
 **Namespace:** std  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [< type_traits >](../standard-library/type-traits.md)



