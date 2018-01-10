---
title: "Bağlayıcı araçları uyarısı LNK4099 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: LNK4099
dev_langs: C++
helpviewer_keywords: LNK4099
ms.assetid: 358170a4-07cd-43fe-918f-82c32757ffc5
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 364c2f9303707328ebf3bdf3284398e6d4f9f0d7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-warning-lnk4099"></a>Bağlayıcı Araçları Uyarısı LNK4099
PDB 'filename' ile 'nesne/Kitaplık' veya 'yolunda'; bulunamadı hata ayıklama bilgileri gibi nesne bağlama  
  
 Bağlayıcı .pdb dosyasını bulamadı. İçerir dizinine kopyalayın `object/library`.  
  
 Nesne dosyayla ilişkili .pdb dosyasının adını bulmak için:  
  
1.  Kitaplıkla nesne dosyasını ayıklamak [lib](../../build/reference/lib-reference.md) **/extract:**`objectname`**.obj** `xyz` **.lib**.  
  
2.  .Pdb dosyasıyla yolunu denetlemek **DUMPBIN /section:.debug$ T /rawdata** `objectname` **.obj**.  
  
 İle derleme [/Z7](../../build/reference/z7-zi-zi-debug-information-format.md), pdb kullanılması ya da kaldırma gerekmez [/DEBUG](../../build/reference/debug-generate-debug-info.md) .pdb dosyaları bağlama nesneler için yoksa bağlayıcı seçeneği.