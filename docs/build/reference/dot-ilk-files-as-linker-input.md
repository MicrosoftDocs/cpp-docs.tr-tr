---
title: . Bağlayıcı girişi olarak Ilk dosyaları | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- ILK files
- .ilk files
ms.assetid: 7324c104-9e5d-423d-b268-b59f92607bf2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 01fea585b86114373017b6d73948cb1438b7185e
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32371690"
---
# <a name="ilk-files-as-linker-input"></a>Bağlayıcı Girişi olarak .Ilk Dosyaları
Artımlı olarak bağlanırken bağlantı ilk artımlı bağlantı sırasında oluşturulan .ilk durum dosyası güncelleştirir. Bu dosyanın .exe veya .dll dosyası aynı temel adı ve uzantısı .ilk varsa. Sonraki artımlı bağlantılar sırasında bağlantı .ilk dosyasını güncelleştirir. .İlk dosyası eksikse, bağlantı tam bağlantısı gerçekleştirir ve yeni bir .ilk dosyası oluşturur. .İlk dosya kullanılamaz ise, bağlantı nonincremental bağlantı gerçekleştirir. Artımlı bağlantılandırma hakkında daha fazla bilgi için bkz [artımlı bağlantı (/ ARTIMLI)](../../build/reference/incremental-link-incrementally.md) seçeneği.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [LINK giriş dosyaları](../../build/reference/link-input-files.md)   
 [Bağlayıcı Seçenekleri](../../build/reference/linker-options.md)