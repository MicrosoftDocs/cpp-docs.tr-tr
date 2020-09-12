---
title: FILE_DATA yapısı
description: C++ derleme öngörüleri SDK FILE_DATA yapısı başvurusu.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- FILE_DATA
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: b5f793df0340005665a8f4ab42e9793f51f3aa0c
ms.sourcegitcommit: 6280a4c629de0f638ebc2edd446de2a9b11f0406
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2020
ms.locfileid: "90041815"
---
# <a name="file_data-structure"></a>FILE_DATA yapısı

::: moniker range="<=vs-2015"

C++ Build Insights SDK 'Sı, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlerin belgelerini görmek için, bu makalenin Visual Studio **Sürüm** Seçicisi denetimini visual Studio 2017 veya visual Studio 2019 olarak ayarlayın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker-end
::: moniker range=">=vs-2017"

`FILE_DATA`Yapı bir dosya girişi veya çıkışı tanımlar.

## <a name="syntax"></a>Syntax

```cpp
typedef struct FILE_DATA_TAG
{
    const wchar_t*      Path;
    int                 TypeCode;

} FILE_DATA;
```

## <a name="members"></a>Üyeler

| Ad | Açıklama |
|--|--|
| `Path` | Dosyanın mutlak yolu |
| `TypeCode` | Dosyanın türünü tanımlayan bir kod. Daha fazla bilgi için bkz. [FILE_TYPE_CODE](file-type-code-enum.md). |

::: moniker-end
