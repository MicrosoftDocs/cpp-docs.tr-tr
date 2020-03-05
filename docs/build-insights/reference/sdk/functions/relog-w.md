---
title: RelogW
description: C++ Build Insights SDK 'Sı RelogW işlev başvurusu.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- RelogW
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 563b1aa92877ff5bc1216bc914c1c661de06dfc0
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/05/2020
ms.locfileid: "78332700"
---
# <a name="relogw"></a>RelogW

::: moniker range="<=vs-2015"

Build C++ Insights SDK 'Sı, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlerin belgelerini görmek için, bu makalenin Visual Studio sürüm Seçicisi denetimini Visual Studio 2017 veya Visual Studio 2019 olarak ayarlayın.

::: moniker-end
::: moniker range=">=vs-2017"

`RelogW` işlevi, Windows için bir giriş olayı Izleme (ETW) izlemesinin MSVC olaylarını okumak ve bunları yeni, değiştirilmiş bir ETW izlemeye yazmak için kullanılır.

## <a name="syntax"></a>Sözdizimi

```cpp
enum RESULT_CODE RelogW(
    const wchar_t*          inputLogFile,
    const wchar_t*          outputLogFile,
    const RELOG_DESCRIPTOR* relogDescriptor);
```

### <a name="parameters"></a>Parametreler

*ınputlogfile*\
Olaylarını okumak istediğiniz giriş ETW izlemesi.

*Outputlogfile*\
Yeni olayların yazılacağı dosya.

*Relogdescriptor*\
[RELOG_DESCRIPTOR](../other-types/relog-descriptor-struct.md) nesnesine yönelik işaretçi. Yeniden günlüğe kaydetme oturumunu yapılandırmak için bu nesneyi kullanın.

### <a name="return-value"></a>Dönüş Değeri

[RESULT_CODE](../other-types/result-code-enum.md) numaralandırmasından elde edilen sonuç kodu.

::: moniker-end
