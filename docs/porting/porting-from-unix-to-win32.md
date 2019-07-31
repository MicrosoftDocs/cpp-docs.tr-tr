---
title: Windows 'da Linux programlarını çalıştırma
ms.date: 07/31/2019
helpviewer_keywords:
- Linux [C++], porting to Win32
ms.assetid: 3837e4fe-3f96-4f24-b2a1-7be94718a881
ms.openlocfilehash: 6b59d7685aaada3ba44c03da2e5c27c75c8a473a
ms.sourcegitcommit: 725e86dabe2901175ecc63261c3bf05802dddff4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/31/2019
ms.locfileid: "68682383"
---
# <a name="running-linux-programs-on-windows"></a>Windows 'da Linux programlarını çalıştırma

Windows üzerinde bir Linux programı çalıştırmak için şu seçeneklere sahipsiniz:

- Programı Linux (WSL) için Windows alt sisteminde olduğu gibi çalıştırın. WSL 'de, programınız bir sanal makinede değil doğrudan makine donanımında yürütülür. WSL ayrıca Windows ve Linux sistemleri arasında doğrudan dosya sistemi çağrılarını, SSL taşıması gereksinimini ortadan kaldırır. WSL, bir komut satırı ortamı olarak tasarlanmıştır ve grafik yoğun uygulamalar için önerilmez. Daha fazla bilgi için bkz. [Linux Için Windows alt sistemi belgeleri](/windows/wsl/about).
- Programı yerel makinenizde veya Azure 'da bir Linux sanal makinesinde ya da Docker kapsayıcısında olduğu gibi çalıştırın. Daha fazla bilgi için bkz. Azure 'da [sanal makineler](https://azure.microsoft.com/services/virtual-machines/) ve [Docker](https://docs.microsoft.com/azure/docker/).
- Linux 'tan Windows Sistem çağrılarına bir çeviri katmanı sağlayan [MinGW](http://MinGW.org/) veya [MinGW-W64](https://MinGW-w64.org/doku.php) ortamlarında GCC veya Clang kullanarak programı derleyin.
- Windows üzerinde MinGW veya MinGW-W64 ile karşılaştırıldığında daha tam bir Linux ortamı sağlayan [Cygwin](https://www.cygwin.com/) ortamındaki GCC veya Clang kullanarak programı derleyin ve çalıştırın.
- Linux 'tan kodunuzu el ile bağlantı noktası ile Microsoft C++ (MSVC) kullanarak Windows için derleyin. Bu, platformdan bağımsız kodu ayrı kitaplıklara yeniden düzenlemeyi ve sonra Windows 'a özel kod (örneğin, Win32 veya DirectX API 'Leri) kullanmak için Linux 'a özgü kodu yeniden yazmayı içerir. Yüksek performanslı grafikler gerektiren uygulamalar için bu büyük olasılıkla en iyi seçenektir.

