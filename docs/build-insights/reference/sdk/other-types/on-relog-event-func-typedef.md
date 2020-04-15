---
title: OnRelogEventFunc typedef
description: C++ Build Insights SDK OnRelogEventFunc typedef referans.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- OnRelogEventFunc
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 2df8646d530c089b1239978d716b2b619a5b4b61
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81329078"
---
# <a name="onrelogeventfunc-typedef"></a>OnRelogEventFunc typedef

::: moniker range="<=vs-2015"

C++ Build Insights SDK, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlere ait belgeleri görmek için, bu makalenin Visual Studio **Sürüm** seçici denetimini Visual Studio 2017 veya Visual Studio 2019 olarak ayarlayın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker-end
::: moniker range=">=vs-2017"

`OnRelogEventFunc` [Typedef, RELOG_CALLBACKS](relog-callbacks-struct.md) yapısında kullanılan işlev imzalarından biridir.

## <a name="syntax"></a>Sözdizimi

```cpp
typedef enum CALLBACK_CODE (BUILD_INSIGHTS_API *OnRelogEventFunc)(
    const EVENT_COLLECTION_DATA*    eventStack,
    const void*                     relogSession,
    void*                           callbackContext);
```

### <a name="parameters"></a>Parametreler

*eventStack*\
Geçerli olay için olay yığını. Olay yığınları hakkında daha fazla bilgi için [Etkinlikler'e](../event-table.md)bakın.

*relogSession*\
[InjectEvent'i](../functions/inject-event.md)ararken kullanılacak oturum işaretçisini yeniden günlüğe kaydetme.

*geri aramaBağlam*\
[bu](analysis-descriptor-struct.md)geri arama için RELOG_DESCRIPTOR olarak ayarlanan bağlam değeri.

### <a name="return-value"></a>Dönüş Değeri

Bir sonraki adımı kontrol eden [CALLBACK_CODE](callback-code-enum.md) bir değer.

::: moniker-end
