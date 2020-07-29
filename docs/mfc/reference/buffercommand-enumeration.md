---
title: BufferCommand numaralandırması
description: 'CMemFile:: GetBufferPtr () aracılığıyla bellek dosyalarıyla çalışmak için kullanılan BufferCommand sabit listesini açıklar'
ms.date: 07/23/2020
f1_keywords:
- afx/buffercommand
helpviewer_keywords:
- buffercommand enumeration [MFC]
ms.openlocfilehash: f2f553df56fadd99b65b04cce9a97917425ed70b
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87246120"
---
# <a name="buffercommand-enumeration"></a>BufferCommand numaralandırması

Dosya destekli bellek arabelleğinde hangi eylemin yapılacağını belirlemek için [CMemFile:: GetBufferPtr](cmemfile-class.md#getbufferptr) tarafından kullanılır.

## <a name="syntax"></a>Sözdizimi

``` cpp
public enum BufferCommand
{
   bufferRead,
   bufferWrite,
   bufferCommit,
   bufferCheck
};
```

## <a name="members"></a>Üyeler

|Ad|Açıklama|
|-|-|
| `bufferRead` | Dosya ile desteklenen bellek arabelleğini okuyun. |
| `bufferWrite` | Dosya ile desteklenen bellek arabelleğine yazın. |
| `bufferCommit` | Dosya ile desteklenen bellek arabelleğindeki geçerli konumu, işlenen arabelleğin sonuna ilerletir. |
| `bufferCheck` | Dosya ile desteklenen bellek arabelleğinin boyutunu büyütüp büyümeyeceğini belirleme. |

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxwinforms. h (derlemede tanımlanan atlmfc\lib\mfcmifc80.dll)
