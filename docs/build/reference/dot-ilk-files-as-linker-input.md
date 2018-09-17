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
ms.openlocfilehash: f3b8de3758daf59a543cdcc9f3b73e1d6c6f0ce8
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45720596"
---
# <a name="ilk-files-as-linker-input"></a>Bağlayıcı Girişi olarak .Ilk Dosyaları

Artımlı bağlantılandırma, bağlantı ilk artımlı bağlantı sırasında oluşturulan .ilk durum dosyası güncelleştirir. Bu dosya .exe veya .dll dosyası olarak aynı temel ada sahiptir ve uzantı .ilk vardır. Sonraki artımlı bağlantılar sırasında bağlantı .ilk dosyası güncelleştirir. .İlk dosyası eksikse, bağlantı tam bağlantı gerçekleştirir ve yeni bir .ilk dosyası oluşturur. .İlk dosyası kullanılamıyor, artımlı olmayan bir bağlantı bağlantı gerçekleştirir. Artımlı bağlama hakkında daha fazla ayrıntı için bkz [artımlı bağlantı (/ INCREMENTAL)](../../build/reference/incremental-link-incrementally.md) seçeneği.

## <a name="see-also"></a>Ayrıca Bkz.

[LINK Giriş Dosyaları](../../build/reference/link-input-files.md)<br/>
[Bağlayıcı Seçenekleri](../../build/reference/linker-options.md)