---
title: LIB giriş dosyaları | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- Lib
dev_langs:
- C++
helpviewer_keywords:
- input files, LIB
ms.assetid: e1236f0d-cd90-446b-b900-f311f456085c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 140a0f1d9ef6fdb3ca5e6d6977804684c88af1fb
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32371973"
---
# <a name="lib-input-files"></a>LIB Giriş Dosyaları
LIB tarafından beklenen giriş dosyaları aşağıdaki tabloda gösterildiği gibi çünkü kullanılıyor, modunu bağlıdır.  
  
|Mod|Giriş|  
|----------|-----------|  
|Varsayılan (derleme veya bir kitaplık değiştirme)|COFF nesne (.obj) dosyaları, COFF kitaplıklarını (.lib), 32-bit nesne modeli biçimi (OMF) nesne (.obj) dosyaları|  
|/ Extract sahip bir üye ayıklanıyor|COFF kitaplık (.lib)|  
|Bir verme dosya oluşturup/def kitaplıkla alma|Modül-tanımlama (.def) dosyası, COFF nesne (.obj) dosyaları, COFF kitaplıklarını (.lib), 32-bit OMF nesne (.obj) dosyaları|  
  
> [!NOTE]
>  OMF kitaplıkları LIB 16-bit sürümü ile oluşturulmuş LIB 32-bit sürümünü girdi olarak kullanılamaz.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [LIB'e Genel Bakış](../../build/reference/overview-of-lib.md)