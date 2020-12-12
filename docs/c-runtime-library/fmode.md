---
description: 'Hakkında daha fazla bilgi edinin: _fmode'
title: _fmode
ms.date: 11/04/2016
f1_keywords:
- fmode
- _fmode
helpviewer_keywords:
- file translation [C++], default mode
- fmode function
- _fmode function
ms.assetid: ac6df9eb-e5cc-4c54-aff3-373c21983118
ms.openlocfilehash: c4e7932369a2ad63b5498078e46cd5610b679ee0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97303937"
---
# <a name="_fmode"></a>_fmode

`_fmode`Değişken, metin veya ikili çeviri için varsayılan dosya çeviri modunu ayarlar. Bu genel değişken, genel değişken yerine kullanılması gereken [_get_fmode](../c-runtime-library/reference/get-fmode.md) ve [_set_fmode](../c-runtime-library/reference/set-fmode.md)daha güvenli işlevsel sürümler için kullanımdan kaldırılmıştır. Aşağıdaki gibi Stdlib. h içinde bildirilmiştir.

## <a name="syntax"></a>Syntax

```
extern int _fmode;
```

## <a name="remarks"></a>Açıklamalar

Varsayılan ayarı, `_fmode` `_O_TEXT` metin modu çevirisi içindir. `_O_BINARY` , ikili mod ayarıdır.

Değerini `_fmode` üç şekilde değiştirebilirsiniz:

- Binmode. obj ile bağlayın. Bu, ' nin başlangıç ayarını olarak değiştirir, ve,, `_fmode` `_O_BINARY` ve dışındaki tüm dosyalara `stdin` `stdout` `stderr` ikili modda açılabilir.

- `_get_fmode` `_set_fmode` Genel değişkeni sırasıyla almak veya ayarlamak için veya ' a çağrı yapın `_fmode` .

- Değerini `_fmode` programınızda ayarlayarak doğrudan değerini değiştirin.

## <a name="see-also"></a>Ayrıca bkz.

[Genel değişkenler](../c-runtime-library/global-variables.md)<br/>
[_get_fmode](../c-runtime-library/reference/get-fmode.md)<br/>
[_set_fmode](../c-runtime-library/reference/set-fmode.md)
