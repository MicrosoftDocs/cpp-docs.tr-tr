---
description: ': Oluşturma hakkında daha fazla bilgi edinin. Sbr dosyası'
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
ms.openlocfilehash: 7f3e056418fe1716dc0130330b09c369e9bdceff
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97196925"
---
# <a name="creating-an-sbr-file"></a>.Sbr Dosyası Oluşturma

> [!WARNING]
> BSCMAKE, Visual Studio ile hala yüklü olsa da artık IDE tarafından kullanılmıyor. Visual Studio 2008 ' den itibaren, gezinme ve sembol bilgileri çözüm klasöründeki bir SQL Server. sdf dosyasında otomatik olarak depolanır.

BSCMAKE için giriş dosyaları. sbr dosyalarıdır. Derleyici, derlediğinde her nesne dosyası (. obj) için bir. sbr dosyası oluşturur. Tarama bilgileri dosyanızı oluştururken veya güncelleştirdiğinizde, projenizin tüm. sbr dosyaları diskte kullanılabilir olmalıdır.

Tüm olası bilgilerle bir. sbr dosyası oluşturmak için [/fr](fr-fr-create-dot-sbr-file.md)öğesini belirtin.

Yerel semboller içermeyen bir. sbr dosyası oluşturmak için [/fr](fr-fr-create-dot-sbr-file.md)öğesini belirtin. . Sbr dosyaları yerel semboller içeriyorsa, BSCMAKE 'in [/el seçeneğini](bscmake-options.md) kullanarak bunları. bsc dosyasından atlayabilirsiniz`.`

Tam derleme yapmadan bir. sbr dosyası oluşturabilirsiniz. Örneğin, bir sözdizimi denetimi gerçekleştirmek için derleyici için/ZS seçeneğini belirtebilir ve/FR veya/Frbelirtirseniz, yine de bir. sbr dosyası oluşturabilirsiniz.

. Sbr dosyaları, başvurulmayan tanımları kaldırmak için ilk kez paketlenayarlanırsa yapı işlemi daha verimli olabilir. Derleyici. sbr dosyalarını otomatik olarak paketledir.

## <a name="see-also"></a>Ayrıca bkz.

[Oluşturma. BSC dosyası](building-a-dot-bsc-file.md)
