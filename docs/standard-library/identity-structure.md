---
title: identity Yapısı
ms.date: 11/04/2016
f1_keywords:
- utility/std::identity
helpviewer_keywords:
- identity class
- identity structure
ms.assetid: 990756fd-7969-4b39-ad7e-0878e8dac8fd
ms.openlocfilehash: 722eb9c0579d0c07765434127d0a7c43718fbc37
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62405007"
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

|Parametre|Açıklama|
|---------------|-----------------|
|*Sol*|Tanımlamak için değeri.|

## <a name="remarks"></a>Açıklamalar

Sınıfı ortak tür tanımını içeren `type`, şablon parametre türü ile aynı olduğu. Şablon işlevi ile birlikte kullanılan [İleri](../standard-library/utility-functions.md#forward) bir işlev parametresi istenen türde olduğundan emin olmak için.

Eski kod ile uyumluluk için sınıf IDENTITY işlevi de tanımlar `operator()` bağımsız değişkenini döndürür *sol*.

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<yardımcı programı >

**Namespace:** std

## <a name="see-also"></a>Ayrıca bkz.

[\<yardımcı programı >](../standard-library/utility.md)<br/>
