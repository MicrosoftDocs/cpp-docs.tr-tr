---
title: FILE_TYPE_CODE enum
description: C++ Build Insights SDK FILE_TYPE_CODE enum referans.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- FILE_TYPE_CODE
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: dea603a072d7b2f472112a75b2e9ccded78399a9
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81325559"
---
# <a name="file_type_code-enum"></a>FILE_TYPE_CODE enum

::: moniker range="<=vs-2015"

C++ Build Insights SDK, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlere ait belgeleri görmek için, bu makalenin Visual Studio **Sürüm** seçici denetimini Visual Studio 2017 veya Visual Studio 2019 olarak ayarlayın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker-end
::: moniker range=">=vs-2017"

Enum `FILE_TYPE_CODE` bir dosyanın türünü açıklar.

## <a name="members"></a>Üyeler

| Adı | Değer | Açıklama |
|--|--|--|
| `FILE_TYPE_CODE_OTHER` | 0 (0x0000000) | Bu enumda listelenmemiş bir dosya türü. |
| `FILE_TYPE_CODE_OBJ` | 1 (0x00000001) | Bir nesne\*( .obj) dosyası. |
| `FILE_TYPE_CODE_EXECUTABLE_IMAGE` | 2 (0x00000002) | Yürütülebilir\*( .exe) veya\*DLL (.dll) dosyası. |
| `FILE_TYPE_CODE_LIB` | 3 (0x00000003) | Statik kitaplık (*.lib) dosyası. |
| `FILE_TYPE_CODE_IMP_LIB` | 4 (0x00000004) | Alma kitaplığı (*.lib) |
| `FILE_TYPE_CODE_EXP` | 5 (0x00000005) | Bir dışa aktarma (*.exp) dosyası. |

## <a name="remarks"></a>Açıklamalar

::: moniker-end
