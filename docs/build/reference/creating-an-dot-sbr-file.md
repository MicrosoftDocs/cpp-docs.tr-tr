---
title: Oluşturma bir. SBR dosya | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ac872dd13458c3fe15971f30a72b06e5510c5bd0
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45723690"
---
# <a name="creating-an-sbr-file"></a>.Sbr Dosyası Oluşturma

BSCMAKE giriş dosyalarına .sbr dosyalarıdır. Derleyici, derleme her nesne dosyası (.obj) .sbr dosyası oluşturur. Derleme veya göz atma bilgisi dosyanızı güncelleştirin, projeniz için tüm .sbr dosyaları diskte mevcut olması gerekir.

Tüm olası bilgilerle .sbr dosyası oluşturmak için belirtin [/FR](../../build/reference/fr-fr-create-dot-sbr-file.md).

Yerel semboller içermeyen .sbr dosyası oluşturmak için belirtin [/Fr](../../build/reference/fr-fr-create-dot-sbr-file.md). .Sbr dosyaları yerel semboller içeriyorsa, yine de bunları .bsc dosyasından BSCMAKE'ın kullanarak atlayabilirsiniz [/El seçeneği](../../build/reference/bscmake-options.md)`.`

Tam derleme yapmadan .sbr dosyası oluşturabilirsiniz. Örneğin, bir sözdizimi denetimi gerçekleştirmek ve /FR veya /Fr. belirtirseniz hala .sbr dosyası oluşturmak için derleyicinin /Zs seçeneğini belirtebilirsiniz.

Yapı işlemi .sbr dosyaları başvurulmayan tanımlarını kaldırmak için ilk paketlenir eklenirse daha verimli olabilir. Derleyici, .sbr dosyaları otomatik olarak paketler.

## <a name="see-also"></a>Ayrıca Bkz.

[.Bsc Dosyası Derleme](../../build/reference/building-a-dot-bsc-file.md)