---
title: FILE_TYPE_CODE numaralandırması
description: C++ Derleme ÖNGÖRÜLERI SDK FILE_TYPE_CODE enum başvurusu.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- FILE_TYPE_CODE
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: e64f9315c62ce40c436032d6c96fdfa725847a7f
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/05/2020
ms.locfileid: "78333722"
---
# <a name="file_type_code-enum"></a>FILE_TYPE_CODE numaralandırması

::: moniker range="<=vs-2015"

Build C++ Insights SDK 'Sı, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlerin belgelerini görmek için, bu makalenin Visual Studio sürüm Seçicisi denetimini Visual Studio 2017 veya Visual Studio 2019 olarak ayarlayın.

::: moniker-end
::: moniker range=">=vs-2017"

`FILE_TYPE_CODE` numaralandırması bir dosyanın türünü açıklar.

## <a name="members"></a>Üyeler

| Adı | Değer | Açıklama |
|--|--|--|
| `FILE_TYPE_CODE_OTHER` | 0 (0x00000000) | Bu sabit listesinde listelenmeyen bir dosya türü. |
| `FILE_TYPE_CODE_OBJ` | 1 (0x00000001) | Bir nesne (\*. obj) dosyası. |
| `FILE_TYPE_CODE_EXECUTABLE_IMAGE` | 2 (0x00000002) | Yürütülebilir (\*. exe) veya DLL (\*. dll) dosyası. |
| `FILE_TYPE_CODE_LIB` | 3 (0x00000003) | Statik kitaplık (*. lib) dosyası. |
| `FILE_TYPE_CODE_IMP_LIB` | 4 (0x00000004) | İçeri aktarma kitaplığı (*. lib) |
| `FILE_TYPE_CODE_EXP` | 5 (0x00000005) | Dışarı aktarma (*. exp) dosyası. |

## <a name="remarks"></a>Açıklamalar

::: moniker-end
