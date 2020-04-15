---
title: MakeStaticReloggerGroup
description: C++ Build Insights SDK MakeStaticReloggerGroup fonksiyon başvurusu.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- MakeStaticReloggerGroup
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 75b638537cb8e0cdeeb5476a3f5277e8e90d9baf
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81323909"
---
# <a name="makestaticreloggergroup"></a>MakeStaticReloggerGroup

::: moniker range="<=vs-2015"

C++ Build Insights SDK, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlere ait belgeleri görmek için, bu makalenin Visual Studio **Sürüm** seçici denetimini Visual Studio 2017 veya Visual Studio 2019 olarak ayarlayın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker-end
::: moniker range=">=vs-2017"

İşlev, `MakeStaticReloggerGroup` [Relog](relog.md)gibi işlevlere geçirilebilen statik bir relogger grubu oluşturmak için kullanılır. Bir relogger grubunun üyeleri, bir izlemedeki tüm olaylar işlenene kadar olayları soldan sağa tektek alır.

## <a name="syntax"></a>Sözdizimi

```cpp
template <typename... TReloggerPtrs>
auto MakeStaticReloggerGroup(TReloggerPtrs... reloggers);
```

### <a name="parameters"></a>Parametreler

*TReloggerPtrs*\
Bu parametre her zaman çıkarılır.

*reloggers*\
Statik relogger grubuna dahil edilen Bir parametre [iRelogger](../other-types/irelogger-class.md) işaretçipaketi. Bu işaretçiler ham `std::unique_ptr`veya `std::shared_ptr`. [IAnalyzer](../other-types/ianalyzer-class.md) işaretçileri `IRelogger` de bir devralma ilişkisi nedeniyle işaretçiler olarak kabul edilir.

### <a name="return-value"></a>Dönüş Değeri

Statik bir relogger grubu. İade değerini yakalamak için **otomatik** anahtar sözcüğü kullanın.

## <a name="remarks"></a>Açıklamalar

Dinamik relogger gruplarının aksine, statik relogger grubunun üyeleri derleme zamanında bilinmelidir. Ayrıca, statik bir relogger grubu çok biçimli davranış yok [IRelogger](../other-types/irelogger-class.md) işaretçileri içerir. Windows için Olay İzleme (ETW) izlemesini çözümlemek için statik bir `IRelogger` relogger grubu kullanırken, arabirime yapılan çağrılar her zaman relogger grup üyesi tarafından doğrudan işaret edilen nesneye gider. Bu esneklik kaybı, daha hızlı olay işleme süreleri olasılığıyla birlikte gelir. Bir relogger grubunun üyeleri derleme zamanında bilinmiyorsa veya işaretçilerinizde `IRelogger` polimorfik davranış gerektiriyorsanız, dinamik bir relogger grubu kullanmayı düşünün. Bunun yerine [MakeDynamicReloggerGroup'u](make-dynamic-relogger-group.md) arayarak dinamik bir relogger grubu kullanabilirsiniz.

::: moniker-end
