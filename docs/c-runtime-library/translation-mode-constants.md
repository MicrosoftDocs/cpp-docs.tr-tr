---
title: Çeviri Modu Sabitleri
ms.date: 11/04/2016
f1_keywords:
- _O_BINARY
- _O_TEXT
- _O_RAW
helpviewer_keywords:
- O_BINARY constant
- O_TEXT constant
- O_RAW constant
- _O_TEXT constant
- _O_RAW constant
- translation constants
- _O_BINARY constant
- translation, constants
- translation, modes
- translation modes (file I/O)
ms.assetid: a5993bf4-7e7a-47f9-83c3-e46332b85579
ms.openlocfilehash: 0b951fc76635f67115f4a832ed316d66b6de7497
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88836705"
---
# <a name="translation-mode-constants"></a>Çeviri Modu Sabitleri

## <a name="syntax"></a>Syntax

```
#include <fcntl.h>
```

## <a name="remarks"></a>Açıklamalar

`_O_BINARY`Ve `_O_TEXT` bildirim sabitleri, dosyalar (ve) için çeviri modunu `_open` `_sopen` veya akışlar () için çeviri modunu belirleme `_setmode` .

İzin verilen değerler şunlardır:

|Değer|Açıklama|
|-|-|
`_O_TEXT`  | Dosyayı metin (çevrilmiş) modunda açar. Satır başı satır besleme (CR-LF) birleşimleri, girişte tek satırlık bir akışa (LF) çevrilir. Satır akış karakterleri, çıkışta CR-LF birleşimlerine çevrilir. Ayrıca CTRL + Z, girişte bir dosya sonu karakteri olarak yorumlanır. Okuma ve yazma için açılan dosyalarda, `fopen` dosyanın sonunda CTRL + Z olup olmadığını denetler ve mümkünse kaldırır. Bu, `fseek` `ftell` CTRL + Z ile biten bir dosya içinde hareket etmek için ve işlevlerinin kullanılması, `fseek` dosyanın sonuna doğru şekilde davranmasına neden olabileceğinden, yapılır.
`_O_BINARY`  | Dosyayı ikili (çevrilmemiş) modda açar. Yukarıdaki Çeviriler bastırılır.
`_O_RAW`  | Aynı `_O_BINARY` . C 2,0 uyumluluğu için desteklenir.

Daha fazla bilgi için bkz. [metin ve Ikili mod dosyası g/ç](../c-runtime-library/text-and-binary-mode-file-i-o.md) ve [Dosya çevirisi](../c-runtime-library/file-translation-constants.md).

## <a name="see-also"></a>Ayrıca bkz.

[_open, _wopen](../c-runtime-library/reference/open-wopen.md)<br/>
[_pipe](../c-runtime-library/reference/pipe.md)<br/>
[_sopen, _wsopen](../c-runtime-library/reference/sopen-wsopen.md)<br/>
[_setmode](../c-runtime-library/reference/setmode.md)<br/>
[Global sabitler](../c-runtime-library/global-constants.md)
