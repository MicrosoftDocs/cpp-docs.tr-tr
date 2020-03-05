---
title: FILE_DATA yapısı
description: C++ Derleme ÖNGÖRÜLERI SDK FILE_DATA yapısı başvurusu.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- FILE_DATA
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 72cae8c8eb81bdb8d94897c46c5af90c89e92ab4
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/05/2020
ms.locfileid: "78333757"
---
# <a name="file_data-structure"></a>FILE_DATA yapısı

::: moniker range="<=vs-2015"

Build C++ Insights SDK 'Sı, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlerin belgelerini görmek için, bu makalenin Visual Studio sürüm Seçicisi denetimini Visual Studio 2017 veya Visual Studio 2019 olarak ayarlayın.

::: moniker-end
::: moniker range=">=vs-2017"

`FILE_DATA` yapısı bir dosya girişi veya çıkışı tanımlar.

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
| `TypeCode` | Dosyanın türünü tanımlayan bir kod. Daha fazla bilgi için bkz. [FILE_TYPE_CODE](file-type-code-enum.md). |

::: moniker-end
