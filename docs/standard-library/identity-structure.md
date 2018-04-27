---
title: identity yapısı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- utility/std::identity
dev_langs:
- C++
helpviewer_keywords:
- identity class
- identity structure
ms.assetid: 990756fd-7969-4b39-ad7e-0878e8dac8fd
caps.latest.revision: 15
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 991333f279053d19ec27fda86ea0bf769371fd90
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="identity-structure"></a>identity Yapısı

Şablon parametresi olarak bir tür tanımı sağlar yapısı.

## <a name="syntax"></a>Sözdizimi

```cpp
struct identity {
   typedef Type type;
   Type operator()(const Type& left) const;
   };
```
### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|`left`|Tanımlamak için değer.|

## <a name="remarks"></a>Açıklamalar

Sınıfı ortak türü tanımını içeren `type`, şablon parametre türü ile aynı olduğu. Şablon işlevi ile birlikte kullanılan [İleri](../standard-library/utility-functions.md#forward) bir işlev parametresi da istenen türe sahip olduğundan emin olmak için.

Eski kod ile uyumluluk için sınıfı ayrıca IDENTITY işlevi tanımlayan `operator()` bağımsız değişkeni döndürür `left`.

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<yardımcı programı >

**Namespace:** std

## <a name="see-also"></a>Ayrıca bkz.

[\<yardımcı programı >](../standard-library/utility.md)<br/>
