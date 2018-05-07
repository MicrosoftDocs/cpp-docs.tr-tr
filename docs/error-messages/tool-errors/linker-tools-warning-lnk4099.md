---
title: Bağlayıcı araçları uyarısı LNK4099 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK4099
dev_langs:
- C++
helpviewer_keywords:
- LNK4099
ms.assetid: 358170a4-07cd-43fe-918f-82c32757ffc5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 22764705b35b2e882c5a03e819c9812d084dc118
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="linker-tools-warning-lnk4099"></a>Bağlayıcı Araçları Uyarısı LNK4099
PDB 'filename' ile 'nesne/Kitaplık' veya 'yolunda'; bulunamadı hata ayıklama bilgileri gibi nesne bağlama  
  
 Bağlayıcı .pdb dosyasını bulamadı. İçerir dizinine kopyalayın `object/library`.  
  
 Nesne dosyayla ilişkili .pdb dosyasının adını bulmak için:  
  
1.  Kitaplıkla nesne dosyasını ayıklamak [lib](../../build/reference/lib-reference.md) **/extract:**`objectname`**.obj** `xyz` **.lib**.  
  
2.  .Pdb dosyasıyla yolunu denetlemek **DUMPBIN /section:.debug$ T /rawdata** `objectname` **.obj**.  
  
 İle derleme [/Z7](../../build/reference/z7-zi-zi-debug-information-format.md), pdb kullanılması ya da kaldırma gerekmez [/DEBUG](../../build/reference/debug-generate-debug-info.md) .pdb dosyaları bağlama nesneler için yoksa bağlayıcı seçeneği.