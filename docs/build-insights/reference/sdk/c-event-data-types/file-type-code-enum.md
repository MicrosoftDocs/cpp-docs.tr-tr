---
title: FILE_TYPE_CODE numaralandırması
description: C++ Build Insights SDK 'Sı FILE_TYPE_CODE enum başvurusu.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- FILE_TYPE_CODE
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: ddd625829e94786c0daddf0e78b914e225b2ecfb
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/29/2020
ms.locfileid: "92921029"
---
# <a name="file_type_code-enum"></a>FILE_TYPE_CODE numaralandırması

::: moniker range="<=msvc-140"

C++ Build Insights SDK 'Sı, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlerin belgelerini görmek için, bu makalenin Visual Studio **Sürüm** Seçicisi denetimini visual Studio 2017 veya visual Studio 2019 olarak ayarlayın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker-end
::: moniker range=">=msvc-150"

`FILE_TYPE_CODE`Sabit listesi bir dosyanın türünü açıklar.

## <a name="members"></a>Üyeler

| Ad | Değer | Açıklama |
|--|--|--|
| `FILE_TYPE_CODE_OTHER` | 0 (0x00000000) | Bu sabit listesinde listelenmeyen bir dosya türü. |
| `FILE_TYPE_CODE_OBJ` | 1 (0x00000001) | Bir nesne ( \* . obj) dosyası. |
| `FILE_TYPE_CODE_EXECUTABLE_IMAGE` | 2 (0x00000002) | Yürütülebilir ( \* . exe) veya dll ( \* . dll) dosyası. |
| `FILE_TYPE_CODE_LIB` | 3 (0x00000003) | Statik kitaplık (*. lib) dosyası. |
| `FILE_TYPE_CODE_IMP_LIB` | 4 (0x00000004) | İçeri aktarma kitaplığı (*. lib) |
| `FILE_TYPE_CODE_EXP` | 5 (0x00000005) | Dışarı aktarma (*. exp) dosyası. |

## <a name="remarks"></a>Açıklamalar

::: moniker-end
