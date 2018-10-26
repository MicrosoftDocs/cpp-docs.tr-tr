---
title: auto_inline | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- auto_inline_CPP
- vc-pragma.auto_inline
dev_langs:
- C++
helpviewer_keywords:
- pragmas, auto_inline
- auto_inline pragma
ms.assetid: f7624cd1-be76-429a-881c-65c9040acf43
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: cc2fb4cb870ff1dca2f0b55e9aad20741ffb8220
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/25/2018
ms.locfileid: "50083184"
---
# <a name="autoinline"></a>auto_inline
Aralık içinde tanımlanan tüm işlevleri hariç burada **kapalı** otomatik satır içi genişletme için aday olarak kabul belirtilir.

## <a name="syntax"></a>Sözdizimi

```
#pragma auto_inline( [{on | off}] )
```

## <a name="remarks"></a>Açıklamalar

Kullanılacak **auto_inline** pragması, öncesinde ve sonrasında hemen getirin (içinde değil) bir işlev tanımı. Pragma görüldüğünde sonra pragma ilk fonksiyon tanımında etkili olur.

## <a name="see-also"></a>Ayrıca Bkz.

[Pragma Yönergeleri ve __Pragma Anahtar Sözcüğü](../preprocessor/pragma-directives-and-the-pragma-keyword.md)