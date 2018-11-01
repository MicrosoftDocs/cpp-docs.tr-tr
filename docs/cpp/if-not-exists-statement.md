---
title: __if_not_exists Deyimi
ms.date: 11/04/2016
f1_keywords:
- __if_not_exists_cpp
helpviewer_keywords:
- __if_not_exists keyword [C++]
ms.assetid: a2f322d4-e96f-4a32-954e-4323d20c6e32
ms.openlocfilehash: d7d172df584200ccc508b281147abf3fa7774952
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50629118"
---
# <a name="ifnotexists-statement"></a>__if_not_exists Deyimi

**__İf_not_exists** deyimi belirtilen tanımlayıcı var olup olmadığını test eder. Tanımlayıcı mevcut değilse, belirtilen deyim bloğu yürütülür.

## <a name="syntax"></a>Sözdizimi

```
__if_not_exists ( identifier ) { 
statements
};
```

#### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*tanımlayıcı*|Test etmek istediğiniz varlığı tanımlayıcısı.|
|*Deyimleri*|Bir veya daha fazla deyimlerini *tanımlayıcı* yok.|

## <a name="remarks"></a>Açıklamalar

> [!CAUTION]
>  En güvenilir sonuçlar elde etmek için kullanın **__if_not_exists** deyiminin altında aşağıdaki kısıtlamalar geçerlidir.

- Uygulama **__if_not_exists** deyimi yalnızca basit türlere, şablon yok.

- Uygulama **__if_not_exists** deyimi içinde veya dışında bir sınıf tanımlayıcıları. Geçerli **__if_not_exists** yerel değişkenlere deyimi.

- Kullanım **__if_not_exists** deyimi yalnızca bir işlev gövdesinin içinde. Bir işlev gövdesinin dışında **__if_not_exists** deyimi tam olarak tanımlanmamış türlerden yalnızca test edebilirsiniz.

- Aşırı yüklenmiş işlevler için test ettiğinizde, belirli bir aşırı yükleme form için test edilemez.

Tamamlayan **__if_not_exists** deyimi [__if_exists](../cpp/if-exists-statement.md) deyimi.

## <a name="example"></a>Örnek

Nasıl kullanılacağı hakkında bir örnek **__if_not_exists**, bkz: [__if_exists deyimi](../cpp/if-exists-statement.md).

## <a name="see-also"></a>Ayrıca bkz.

[Seçim Deyimleri](../cpp/selection-statements-cpp.md)<br/>
[Anahtar Sözcükler](../cpp/keywords-cpp.md)<br/>
[__if_exists Deyimi](../cpp/if-exists-statement.md)