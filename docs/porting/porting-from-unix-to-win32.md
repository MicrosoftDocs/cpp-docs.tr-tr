---
title: Windows’da Linux programları çalıştırma
ms.date: 07/31/2019
helpviewer_keywords:
- Linux [C++], porting to Win32
ms.assetid: 3837e4fe-3f96-4f24-b2a1-7be94718a881
ms.openlocfilehash: c91bcf1c9384cd71811d42a14b98dc155626a4d5
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81368465"
---
# <a name="running-linux-programs-on-windows"></a>Windows’da Linux programları çalıştırma

Windows'da bir Linux programı çalıştırmak için şu seçeneklere sahipsiniz:

- Programı Linux için Windows Alt Sistemi'nde (WSL) olduğu gibi çalıştırın. WSL'de programınız sanal bir makinede değil, doğrudan makine donanımında yürütülür. WSL ayrıca Windows ve Linux sistemleri arasında doğrudan dosya sistemi çağrıları na olanak sağlayarak SSL taşıma gereksinimini ortadan kaldırır. WSL komut satırı ortamı olarak tasarlanmıştır ve grafik yoğun uygulamalar için önerilmez. Daha fazla bilgi [için Linux Belgeleri için Windows Alt Sistemi'ne](/windows/wsl/about)bakın.
- Programı, yerel makinenizde veya Azure'da bir Linux sanal makineveya Docker konteynerinde olduğu gibi çalıştırın. Daha fazla bilgi için Azure'da [Sanal Makineler](https://azure.microsoft.com/services/virtual-machines/) ve [Docker'a](https://docs.microsoft.com/azure/docker/)bakın.
- Programı, Linux'tan Windows sistem çağrılarına bir çeviri katmanı sağlayan [MinGW](http://MinGW.org/) veya [MinGW-w64](https://sourceforge.net/p/mingw-w64/wiki2/Home/) ortamlarında gcc veya clang kullanarak derleyin.
- Programı [Cygwin](https://www.cygwin.com/) ortamında gcc veya clang kullanarak çalıştırın ve Windows'da MinGW veya MinGW-w64 ile karşılaştırıldığında daha eksiksiz bir Linux ortamı sağlar.
- Kodunuzu Linux'tan el ile sabitleyin ve Microsoft C++ (MSVC) kullanarak Windows için derleyin. Bu, platformdan bağımsız kodu ayrı kitaplıklara yeniden düzenlemeyi ve ardından Windows'a özgü kodu (örneğin, Win32 veya DirectX API'leri) kullanmak için Linux'a özgü kodu yeniden yazmayı içerir. Yüksek performanslı grafik gerektiren uygulamalar için bu muhtemelen en iyi seçenektir.
