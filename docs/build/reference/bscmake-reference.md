---
description: 'Şu konuda daha fazla bilgi edinin: BSCMAKE başvurusu'
title: BSCMAKE Başvurusu
ms.date: 05/06/2019
helpviewer_keywords:
- BSCMAKE, reference
- Microsoft Browse Information Maintenance Utility
- browse windows
- browse information files (.bsc), building
- .bsc files, building
- bsc files, building
- BSCMAKE
ms.assetid: b97ad994-1355-4809-98db-6abc12c6fb13
ms.openlocfilehash: 11a90561e22b9fb3a39f022ba188e5c9d155e45e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97179435"
---
# <a name="bscmake-reference"></a>BSCMAKE Başvurusu

> [!WARNING]
> BSCMAKE, Visual Studio ile hala yüklü olsa da artık IDE tarafından kullanılmıyor. Visual Studio 2008 ' den itibaren, gezinme ve sembol bilgileri çözüm klasöründeki bir SQL Server. sdf dosyasında otomatik olarak depolanır.

Microsoft tarayıcı bilgi Bakımı yardımcı programı (BSCMAKE.EXE), derleme sırasında oluşturulan. sbr dosyalarından bir tarama bilgi dosyası (. bsc) oluşturur. Bazı üçüncü taraf araçları, kod analizi için. BSC dosyalarını kullanır.

Programınızı derlediğinizde, dosyayı oluşturmak için BSCMAKE kullanarak, programınız için otomatik olarak bir tarama bilgisi dosyası oluşturabilirsiniz. Visual Studio geliştirme ortamında tarama bilgilerinizi dosyanızı oluşturursanız BSCMAKE 'in nasıl çalıştırılacağını bilmeniz gerekmez. Ancak, kullanılabilen seçimleri anlamak için bu konuyu okumak isteyebilirsiniz.

Programınızı geliştirme ortamının dışında oluşturursanız, yine de ortamda inceleyebileceğiniz özel bir. bsc oluşturmaya devam edebilirsiniz. Derleme sırasında oluşturduğunuz. sbr dosyalarında BSCMAKE komutunu çalıştırın.

> [!NOTE]
> Bu aracı yalnızca Visual Studio Geliştirici komut isteminden başlatabilirsiniz. Bunu bir sistem komut isteminden veya dosya Gezgini 'nden başlatamazsınız.

Bu bölüm şu konuları içerir:

- [Göz at bilgi dosyaları oluşturma: genel bakış](building-browse-information-files-overview.md)

- [. Bsc dosyası oluşturma](building-a-dot-bsc-file.md)

- [BSCMAKE komut satırı](bscmake-command-line.md)

- [BSCMAKE komut dosyası](bscmake-command-file-response-file.md)

- [BSCMAKE seçenekleri](bscmake-options.md)

- [BSCMAKE çıkış kodları](bscmake-exit-codes.md)

## <a name="see-also"></a>Ayrıca bkz.

[Ek MSVC derleme araçları](c-cpp-build-tools.md)
