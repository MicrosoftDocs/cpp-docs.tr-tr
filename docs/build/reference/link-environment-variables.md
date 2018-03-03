---
title: "LINK ortam değişkenleri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- link
dev_langs:
- C++
helpviewer_keywords:
- variables, environment
- LINK tool [C++], environment variables
- LIB environment variable
- environment variables [C++], LINK
ms.assetid: 9a3d3291-0cc4-4a7d-9d50-80e351b90708
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 67b36afce92140c4f205f8e5a4a46dfc7ac2d300
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="link-environment-variables"></a>LINK Ortam Değişkenleri

LINK aracı aşağıdaki ortam değişkenlerini kullanır:  
  
-   BAĞLANTI ve \_bağlantı\_, tanımlanmışsa. LINK aracı seçenekleri ve bağlantı ortam değişkeninde tanımlanan bağımsız değişkenleri başına ve seçenekleri ekler ve bağımsız değişkenler tanımlanan \_bağlantı\_ işlemeden önce komut satırı bağımsız değişkenleri için ortam değişkeni.  
  
-   LIB tanımlanmışsa. Bağlantı Araçları kullanır LIB yolu bir nesne, kitaplığı veya komut satırı ya da belirtilen başka bir dosyaya için arama yaparken [/temel](../../build/reference/base-base-address.md) seçeneği. Ayrıca bir nesne adlı bir .pdb dosyasını bulmak için LIB yolunu kullanır. LIB değişkeni noktalı virgülle ayırarak bir veya daha fazla yol belirtimleri içerebilir. Bir yolu, Visual C++ yüklemenizi \lib alt dizinine işaret etmelidir.  
  
-   YOL, aracı CVTRES çalıştırmak için gereken ve bağlantının kendisi ile aynı dizinde dosyayı bulamıyor. (Bağlantı .res dosyasını bağlamak CVTRES gerektirir.) YOL, Visual C++ yüklemenizi \bin alt dizinine işaret etmelidir.  
  
-   TMP, OMF veya .res dosyaları bağlanırken bir dizin belirtin.  
  
## <a name="see-also"></a>Ayrıca Bkz.  

[Bağlayıcı seçeneklerini ayarlama](../../build/reference/setting-linker-options.md)   
[Bağlayıcı seçenekleri](../../build/reference/linker-options.md)   
[Komut satırında C/C++ kodu derleme](../../build/building-on-the-command-line.md)  
[Komut Satırı Derlemeleri için Yolu ve Ortam Değişkenlerini Ayarlama](../../build/setting-the-path-and-environment-variables-for-command-line-builds.md)
