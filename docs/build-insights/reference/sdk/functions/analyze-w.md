---
title: AnalyzeW
description: C++ Build Insights SDK 'Sı Analkaw işlev başvurusu.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- AnalyzeW
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: a75668e0fc9d356315f5f0b3156a909187415521
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/29/2020
ms.locfileid: "92922855"
---
# <a name="analyzew"></a>AnalyzeW

::: moniker range="<=msvc-140"

C++ Build Insights SDK 'Sı, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlerin belgelerini görmek için, bu makalenin Visual Studio **Sürüm** Seçicisi denetimini visual Studio 2017 veya visual Studio 2019 olarak ayarlayın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker-end
::: moniker range=">=msvc-150"

`AnalyzeW`İşlevi, Windows için bir giriş olayı izleme (ETW) izleme 'den okunan MSVC olaylarını çözümlemek için kullanılır.

## <a name="syntax"></a>Sözdizimi

```cpp
enum RESULT_CODE AnalyzeW(
    const wchar_t*             inputLogFile,
    const ANALYSIS_DESCRIPTOR* analysisDescriptor);
```

### <a name="parameters"></a>Parametreler

*ınputlogfile*\
Olaylarını okumak istediğiniz giriş ETW izlemesi.

*analysisDescriptor*\
[ANALYSIS_DESCRIPTOR](../other-types/analysis-descriptor-struct.md) nesnesine yönelik işaretçi. Çözümlemeyi yapılandırmak için bu nesneyi kullanın.

### <a name="return-value"></a>Dönüş Değeri

[RESULT_CODE](../other-types/result-code-enum.md) numaralandırmasından elde edilen sonuç kodu.

::: moniker-end
