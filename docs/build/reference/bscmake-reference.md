---
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
ms.openlocfilehash: f95e34b9599de628463b9f92ebf8f01036237891
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81320733"
---
# <a name="bscmake-reference"></a>BSCMAKE Başvurusu

> [!WARNING]
> BSCMAKE hala Visual Studio yüklü olmasına rağmen, artık IDE tarafından kullanılmaz. Visual Studio 2008'den bu yana, göz atma ve sembol bilgileri çözüm klasöründe bir SQL Server .sdf dosyasında otomatik olarak depolanır.

Microsoft Gözat Bilgi Bakım Programı (BSCMAKE). EXE) derleme sırasında oluşturulan .sbr dosyalarından bir gözatma bilgi dosyası (.bsc) oluşturur. Bazı üçüncü taraf araçları kod analizi için .bsc dosyalarını kullanır.

Programınızı oluştururken, dosyayı oluşturmak için BSCMAKE'yi kullanarak otomatik olarak programınız için bir gözatma bilgi dosyası oluşturabilirsiniz. Visual Studio geliştirme ortamında gözatma bilgi dosyanızı oluşturursanız BSCMAKE'nin nasıl çalıştırılacağını bilmeniz gerekmez. Ancak, mevcut seçenekleri anlamak için bu konuyu okumak isteyebilirsiniz.

Programınızı geliştirme ortamının dışında oluşturursanız, yine de ortamda inceleyeceğiniz özel bir .bsc oluşturabilirsiniz. Derleme sırasında oluşturduğunuz .sbr dosyalarında BSCMAKE'yi çalıştırın.

> [!NOTE]
> Bu aracı yalnızca Visual Studio Developer komut isteminden başlatabilirsiniz. Sistem komut isteminden veya Dosya Gezgini'nden başlatamazsınız.

Bu bölüm şu konuları içerir:

- [Gözatma Bilgileri Dosyası Derleme: Genel Bakış](building-browse-information-files-overview.md)

- [.bsc dosyası oluşturma](building-a-dot-bsc-file.md)

- [BSCMAKE komut satırı](bscmake-command-line.md)

- [BSCMAKE komut dosyası](bscmake-command-file-response-file.md)

- [BSCMAKE seçenekleri](bscmake-options.md)

- [BSCMAKE çıkış kodları](bscmake-exit-codes.md)

## <a name="see-also"></a>Ayrıca bkz.

[Ek MSVC Oluşturma Araçları](c-cpp-build-tools.md)
