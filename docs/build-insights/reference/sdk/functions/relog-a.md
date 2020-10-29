---
title: RelogA
description: C++ Build Insights SDK 'Sı bir işlev başvurusunu yeniden günlüğe alın.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- RelogA
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 4e4882bca2241c520d4cb6ba0a8eb9c32704eaef
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/29/2020
ms.locfileid: "92922804"
---
# <a name="reloga"></a>RelogA

::: moniker range="<=msvc-140"

C++ Build Insights SDK 'Sı, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlerin belgelerini görmek için, bu makalenin Visual Studio **Sürüm** Seçicisi denetimini visual Studio 2017 veya visual Studio 2019 olarak ayarlayın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker-end
::: moniker range=">=msvc-150"

`RelogA`İşlevi, Windows Için olay izleme (ETW) IZLEMESININ MSVC olaylarını okumak ve bunları yeni, değiştirilmiş BIR ETW izlemeye yazmak için kullanılır.

## <a name="syntax"></a>Sözdizimi

```cpp
enum RESULT_CODE RelogA(
    const char*             inputLogFile,
    const char*             outputLogFile,
    const RELOG_DESCRIPTOR* relogDescriptor);
```

### <a name="parameters"></a>Parametreler

*ınputlogfile*\
Olaylarını okumak istediğiniz giriş ETW izlemesi.

*outputLogFile*\
Yeni olayların yazılacağı dosya.

*relogDescriptor*\
[RELOG_DESCRIPTOR](../other-types/relog-descriptor-struct.md) nesnesine yönelik işaretçi. Yeniden günlüğe kaydetme oturumunu yapılandırmak için bu nesneyi kullanın.

### <a name="return-value"></a>Dönüş Değeri

[RESULT_CODE](../other-types/result-code-enum.md) numaralandırmasından elde edilen sonuç kodu.

::: moniker-end
