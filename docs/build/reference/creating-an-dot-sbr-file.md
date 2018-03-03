---
title: "Oluşturma bir. SBR dosya | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- SBR files
- BSCMAKE, input files
- .sbr files
- source browser files
- local symbols in browse information
- symbols
ms.assetid: bdb4b93c-a88a-441a-84fd-01087d03be25
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d87b71daaf5d7b37e67c2c0e56e844bd5251a490
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="creating-an-sbr-file"></a>.Sbr Dosyası Oluşturma
BSCMAKE için girdi dosyaları .sbr dosyalarıdır. Derleyici derlendiğinden her nesne dosyası (.obj) için bir .sbr dosyası oluşturur. Gözatma bilgileri dosyası derleme veya güncelleştirdiğinizde, tüm .sbr dosyaları projeniz için disk üzerinde kullanılabilir olması gerekir.  
  
 Tüm olası bilgilerle .sbr dosyası oluşturmak için belirtmek [/FR](../../build/reference/fr-fr-create-dot-sbr-file.md).  
  
 Yerel semboller içermeyen .sbr dosyası oluşturmak için belirtin [/Fr](../../build/reference/fr-fr-create-dot-sbr-file.md). .Sbr dosyaları yerel semboller içeriyorsa, hala bunları .bsc dosyasından BSCMAKE'ın kullanarak atlayabilirsiniz [/El seçeneği](../../build/reference/bscmake-options.md)`.`  
  
 Tam bir derleme yapmadan .sbr dosyası oluşturabilirsiniz. Örneğin, bir sözdizimi denetimi gerçekleştirmek ve /FR veya /Fr. belirtirseniz, hala .sbr dosyası oluşturmak için derleyici /Zs seçeneğini belirtebilirsiniz  
  
 Derleme işlemi .sbr dosyaları başvurulmayan tanımları kaldırmak için ilk paketlenmiş, daha etkili olabilir. Derleyici .sbr dosyaları otomatik olarak paketler.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [.Bsc Dosyası Derleme](../../build/reference/building-a-dot-bsc-file.md)