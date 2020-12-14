---
description: 'Daha fazla bilgi edinin: kimlik yapısı'
title: identity Yapısı
ms.date: 11/04/2016
f1_keywords:
- utility/std::identity
helpviewer_keywords:
- identity class
- identity structure
ms.assetid: 990756fd-7969-4b39-ad7e-0878e8dac8fd
ms.openlocfilehash: 753a3b697eb2a77dd102f681403fd23d7062cb36
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97231764"
---
# <a name="identity-structure"></a>identity Yapısı

Şablon parametresi olarak bir tür tanımı sağlayan bir struct.

## <a name="syntax"></a>Sözdizimi

```cpp
struct identity {
   typedef Type type;
   Type operator()(const Type& left) const;
};
```

### <a name="parameters"></a>Parametreler

*tarafta*\
Tanımlamak için değer.

## <a name="remarks"></a>Açıklamalar

Sınıfı, `type` şablon parametre türüyle aynı olan ortak tür tanımını içerir. Bir işlev parametresinin istenen türe sahip olduğundan emin olmak için şablon işlevi [İleri](../standard-library/utility-functions.md#forward) ile birlikte kullanılır.

Daha eski kodla uyumluluk için, sınıfı, `operator()` bağımsız değişkenini *sola* döndüren kimlik işlevini de tanımlar.
