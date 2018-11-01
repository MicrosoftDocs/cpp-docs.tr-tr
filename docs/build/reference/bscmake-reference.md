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
ms.openlocfilehash: 1f321d51d1b880ea634c835567767c528aca041b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50509480"
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

- [Gözatma Bilgileri Dosyası Derleme: Genel Bakış](../../build/reference/building-browse-information-files-overview.md)

- [.Bsc dosyası derleme](../../build/reference/building-a-dot-bsc-file.md)

- [BSCMAKE komut satırı](../../build/reference/bscmake-command-line.md)

- [BSCMAKE komut dosyası](../../build/reference/bscmake-command-file-response-file.md)

- [BSCMAKE seçenekleri](../../build/reference/bscmake-options.md)

- [BSCMAKE çıkış kodları](../../build/reference/bscmake-exit-codes.md)

## <a name="see-also"></a>Ayrıca Bkz.

[C/C++ Derleme Araçları](../../build/reference/c-cpp-build-tools.md)