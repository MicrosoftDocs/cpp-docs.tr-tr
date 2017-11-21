---
title: auto_inline | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- auto_inline_CPP
- vc-pragma.auto_inline
dev_langs: C++
helpviewer_keywords:
- pragmas, auto_inline
- auto_inline pragma
ms.assetid: f7624cd1-be76-429a-881c-65c9040acf43
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: cb1a36766f8472b6543e8061d0d2566071f47dc8
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="autoinline"></a>auto_inline
Aralık içinde tanımlanan tüm işlevler dışlar nerede **kapalı** otomatik satır içi genişletme için aday olarak kabul belirtilir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
#pragma auto_inline( [{on | off}] )  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Kullanılacak **auto_inline** pragma, önce ve sonra hemen getirin (içinde değil) bir işlev tanımı. Pragma görülen sonra pragma ilk işlev tanımını etkinleşir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Pragma yönergeleri ve __Pragma anahtar sözcüğü](../preprocessor/pragma-directives-and-the-pragma-keyword.md)