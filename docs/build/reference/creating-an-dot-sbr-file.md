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
ms.openlocfilehash: 6a2e685d33b108ce542fdc6e3e0565cc37299c1c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62294076"
---
# <a name="creating-an-sbr-file"></a>.Sbr Dosyası Oluşturma

> [!WARNING]
> BSCMAKE hala Visual Studio ile yüklenir ancak artık IDE tarafından kullanılır. Visual Studio 2008'den itibaren göz atma ve sembol bilgilerini otomatik olarak bir SQL Server .sdf dosyası çözüm klasöründe depolanır.

BSCMAKE giriş dosyalarına .sbr dosyalarıdır. Derleyici, derleme her nesne dosyası (.obj) .sbr dosyası oluşturur. Derleme veya göz atma bilgisi dosyanızı güncelleştirin, projeniz için tüm .sbr dosyaları diskte mevcut olması gerekir.

Tüm olası bilgilerle .sbr dosyası oluşturmak için belirtin [/FR](fr-fr-create-dot-sbr-file.md).

Yerel semboller içermeyen .sbr dosyası oluşturmak için belirtin [/Fr](fr-fr-create-dot-sbr-file.md). .Sbr dosyaları yerel semboller içeriyorsa, yine de bunları .bsc dosyasından BSCMAKE'ın kullanarak atlayabilirsiniz [/El seçeneği](bscmake-options.md)`.`

Tam derleme yapmadan .sbr dosyası oluşturabilirsiniz. Örneğin, bir sözdizimi denetimi gerçekleştirmek ve /FR veya /Fr. belirtirseniz hala .sbr dosyası oluşturmak için derleyicinin /Zs seçeneğini belirtebilirsiniz.

Yapı işlemi .sbr dosyaları başvurulmayan tanımlarını kaldırmak için ilk paketlenir eklenirse daha verimli olabilir. Derleyici, .sbr dosyaları otomatik olarak paketler.

## <a name="see-also"></a>Ayrıca bkz.

[.Bsc Dosyası Derleme](building-a-dot-bsc-file.md)
