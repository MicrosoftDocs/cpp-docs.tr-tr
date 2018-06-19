---
title: identity yapısı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- utility/std::identity
dev_langs:
- C++
helpviewer_keywords:
- identity class
- identity structure
ms.assetid: 990756fd-7969-4b39-ad7e-0878e8dac8fd
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 83180020c20f78c16af0b1b33bada91936b6af9b
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33844412"
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
