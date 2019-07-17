---
title: identity Yapısı
ms.date: 11/04/2016
f1_keywords:
- utility/std::identity
helpviewer_keywords:
- identity class
- identity structure
ms.assetid: 990756fd-7969-4b39-ad7e-0878e8dac8fd
ms.openlocfilehash: 49b2c1eb3ca03f9bf9199bdbca49348866ff0a7e
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/16/2019
ms.locfileid: "68246158"
---
# <a name="identity-structure"></a>identity Yapısı

Şablon parametresi olarak bir tür tanımı sağlayan bir yapı.

## <a name="syntax"></a>Sözdizimi

```cpp
struct identity {
   typedef Type type;
   Type operator()(const Type& left) const;
};
```

### <a name="parameters"></a>Parametreler

*Sol*\
Tanımlamak için değeri.

## <a name="remarks"></a>Açıklamalar

Sınıfı ortak tür tanımını içeren `type`, şablon parametre türü ile aynı olduğu. Şablon işlevi ile birlikte kullanılan [İleri](../standard-library/utility-functions.md#forward) bir işlev parametresi istenen türde olduğundan emin olmak için.

Eski kod ile uyumluluk için sınıf IDENTITY işlevi de tanımlar `operator()` bağımsız değişkenini döndürür *sol*.
