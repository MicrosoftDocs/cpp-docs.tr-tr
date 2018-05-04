---
title: SAPLAMA | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- STUB
dev_langs:
- C++
helpviewer_keywords:
- STUB .def file statement
ms.assetid: 0a3b9643-19ed-47e9-8173-ee16bc8ed056
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 385e073f877a938a3b73fa79036d27cf50c1e4ec
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="stub"></a>STUB
Bir modül tanım dosyasında sanal aygıt sürücüsü (VxD) derlemeler kullanıldığında (WINNT içinde tanımlanmıştır. IMAGE_DOS_HEADER yapısı içeren bir dosya adı belirtmenize olanak tanır Y) yerine varsayılan başlık sanal aygıt sürücüsü (VxD), kullanılacak.  
  
```  
STUB:filename  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Belirtmek için eşdeğer bir yol *filename* ile [/STUB](../../build/reference/stub-ms-dos-stub-file-name.md) bağlayıcı seçeneği.  
  
 SAPLAMA modül tanım dosyasında yalnızca bir VxD oluştururken geçerlidir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Modül Tanımlama Deyimleri Kuralları](../../build/reference/rules-for-module-definition-statements.md)