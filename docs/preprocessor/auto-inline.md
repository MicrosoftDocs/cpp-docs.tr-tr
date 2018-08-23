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
ms.openlocfilehash: dc1b8a3b8539fb4871e4a28f4635c8012b9f80a2
ms.sourcegitcommit: d4c803bd3a684d7951bf88dcecf1f14af43ae411
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/10/2018
ms.locfileid: "42466161"
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