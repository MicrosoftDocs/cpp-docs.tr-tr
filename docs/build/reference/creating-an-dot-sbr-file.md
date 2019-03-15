---
title: .Sbr Dosyası Oluşturma
ms.date: 11/04/2016
helpviewer_keywords:
- SBR files
- BSCMAKE, input files
- .sbr files
- source browser files
- local symbols in browse information
- symbols
ms.assetid: bdb4b93c-a88a-441a-84fd-01087d03be25
ms.openlocfilehash: 75c3b926a605de66c876e9350218807031cd9a43
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57810412"
---
# <a name="creating-an-sbr-file"></a>.Sbr Dosyası Oluşturma

BSCMAKE giriş dosyalarına .sbr dosyalarıdır. Derleyici, derleme her nesne dosyası (.obj) .sbr dosyası oluşturur. Derleme veya göz atma bilgisi dosyanızı güncelleştirin, projeniz için tüm .sbr dosyaları diskte mevcut olması gerekir.

Tüm olası bilgilerle .sbr dosyası oluşturmak için belirtin [/FR](fr-fr-create-dot-sbr-file.md).

Yerel semboller içermeyen .sbr dosyası oluşturmak için belirtin [/Fr](fr-fr-create-dot-sbr-file.md). .Sbr dosyaları yerel semboller içeriyorsa, yine de bunları .bsc dosyasından BSCMAKE'ın kullanarak atlayabilirsiniz [/El seçeneği](bscmake-options.md)`.`

Tam derleme yapmadan .sbr dosyası oluşturabilirsiniz. Örneğin, bir sözdizimi denetimi gerçekleştirmek ve /FR veya /Fr. belirtirseniz hala .sbr dosyası oluşturmak için derleyicinin /Zs seçeneğini belirtebilirsiniz.

Yapı işlemi .sbr dosyaları başvurulmayan tanımlarını kaldırmak için ilk paketlenir eklenirse daha verimli olabilir. Derleyici, .sbr dosyaları otomatik olarak paketler.

## <a name="see-also"></a>Ayrıca bkz.

[.Bsc Dosyası Derleme](building-a-dot-bsc-file.md)
