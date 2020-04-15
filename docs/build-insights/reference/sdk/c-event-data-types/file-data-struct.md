---
title: FILE_DATA yapısı
description: C++ Build Insights SDK FILE_DATA yapı referansı.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- FILE_DATA
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 6b7b0129c54fa4b1d5285bafb38761da45bab4e5
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81325583"
---
# <a name="file_data-structure"></a>FILE_DATA yapısı

::: moniker range="<=vs-2015"

C++ Build Insights SDK, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlere ait belgeleri görmek için, bu makalenin Visual Studio **Sürüm** seçici denetimini Visual Studio 2017 veya Visual Studio 2019 olarak ayarlayın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker-end
::: moniker range=">=vs-2017"

Yapı, `FILE_DATA` bir dosya girişini veya çıktısını açıklar.

## <a name="syntax"></a>Sözdizimi

```cpp
typedef struct FILE_DATA_TAG
{
    const wchar_t*      Path;
    int                 TypeCode;

} FILE_DATA;
```

## <a name="members"></a>Üyeler

|  |  |
|--|--|
| `Path` | Dosyanın mutlak yolu |
| `TypeCode` | Dosyanın türünü açıklayan bir kod. Daha fazla bilgi için [FILE_TYPE_CODE.](file-type-code-enum.md) |

::: moniker-end
