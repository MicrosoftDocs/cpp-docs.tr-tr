---
title: BSCMAKE Başvurusu
ms.date: 11/04/2016
helpviewer_keywords:
- BSCMAKE, reference
- Microsoft Browse Information Maintenance Utility
- browse windows
- browse information files (.bsc), building
- .bsc files, building
- bsc files, building
- BSCMAKE
ms.assetid: b97ad994-1355-4809-98db-6abc12c6fb13
ms.openlocfilehash: 4303e48e3d02f0f69b177e8a888157a6f90aaa89
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57822359"
---
# <a name="bscmake-reference"></a>BSCMAKE Başvurusu

> [!WARNING]
> BSCMAKE hala Visual Studio ile yüklenir ancak artık IDE tarafından kullanılır. Visual Studio 2008'den itibaren göz atma ve sembol bilgilerini otomatik olarak bir SQL Server .sdf dosyası çözüm klasöründe depolanır.

Microsoft gözatma bilgileri bakım yardımcı programı (BSCMAKE. EXE), derleme sırasında oluşturulan .sbr dosyalarını gözatma bilgisi dosyası (.bsc) oluşturur. Bazı üçüncü taraf araçları için kod analizi .bsc dosyaları kullanın.

Programınızı oluşturma sırasında BSCMAKE dosyasını oluşturmak için kullanarak programınız için gözatma bilgisi dosyası otomatik olarak oluşturabilirsiniz. Visual C++ geliştirme ortamında, gözatma bilgisi dosyası oluşturursanız, BSCMAKE çalıştırma bilmeniz gerekmez. Ancak, seçenekleri anlamak için bu konuyu okumak isteyebilirsiniz.

Programınızı geliştirme ortamı dışında oluşturuyorsanız, geçirebileceğiniz bir özel .bsc ortamda oluşturabilirsiniz. BSCMAKE derleme sırasında oluşturulan .sbr dosyaları çalıştırın.

> [!NOTE]
>  Bu araç yalnızca Visual Studio Geliştirici komut isteminden başlatabilirsiniz. Bir sistem komut satırından veya dosya Gezgini'nden başlatılamıyor.

Bu bölüm şu konuları içerir:

- [Göz Atma Bilgileri Dosyası Derleme: Genel Bakış](building-browse-information-files-overview.md)

- [.Bsc dosyası derleme](building-a-dot-bsc-file.md)

- [BSCMAKE komut satırı](bscmake-command-line.md)

- [BSCMAKE komut dosyası](bscmake-command-file-response-file.md)

- [BSCMAKE seçenekleri](bscmake-options.md)

- [BSCMAKE çıkış kodları](bscmake-exit-codes.md)

## <a name="see-also"></a>Ayrıca bkz.

[Ek MSVC derleme araçları](c-cpp-build-tools.md)
