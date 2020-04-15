---
title: Desteklenen Platformlar (Visual C++)
ms.date: 12/02/2019
ms.technology: cpp-tools
helpviewer_keywords:
- Visual C++, platforms supported
- platforms [C++]
ms.assetid: 0d893056-4008-411a-b3d1-5f57fd7da95c
ms.openlocfilehash: 049b28d23c7f5f5f023f3b2964577b75992c2998
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "75793836"
---
# <a name="supported-platforms-visual-c"></a>Desteklenen Platformlar (Visual C++)

Visual Studio kullanılarak oluşturulmuş uygulamalar aşağıdaki gibi çeşitli platformlara hedeflenebilir.

|İşletim Sistemi|x86|x64|ARM|ARM64\*\*\*\*|
|----------------------|---------|---------|---------|---------|
|Windows XP|X\*|X\*|||
|Windows Server 2003|X\*|X\*|||
|Windows Vista|X|X|||
|Windows Server 2008|X|X|||
|Windows 7|X|X|||
|Windows Server 2012 R2|X|X|||
|Windows 8|X|X|X||
|Windows 8.1|X|X|X||
|Windows 10|X|X|X|X|
|Android\*\*|X|X|X|X|
|Ios\*\*|X|X|X|X|
|Linux\*\*\*|X|X|X|X|

\*Windows XP ve Windows Server 2003 projelerini oluşturmak için Visual Studio 2017, Visual Studio 2015, Visual Studio 2013 ve Visual Studio 2012 Update 1'de yer alan Windows XP platform araç kümesini kullanabilirsiniz. Bu platform araç kümesinin nasıl kullanılacağı hakkında daha fazla bilgi için Windows [XP için Programları Yapılandırma'ya](../build/configuring-programs-for-windows-xp.md)bakın. Platform araç kümesini değiştirme hakkında daha fazla bilgi için [bkz: Hedef Çerçeve ve Platform Araç Kümesini Değiştirin.](../build/how-to-modify-the-target-framework-and-platform-toolset.md)

\*\*Visual Studio 2017 ve sonrası için yükleyiciye C++ iş yükü **yle Mobil geliştirmeyi** yükleyebilirsiniz. Visual Studio 2015 kurulumunda, iOS veya Android platformlarını hedeflemek için Çapraz Platform Mobil Geliştirme bileşeni için isteğe bağlı **Visual C++** seçeneğini belirleyin. Talimatlar [için, Platformötesi Mobil Geliştirme için Görsel C++ Yükle'ye](/visualstudio/cross-platform/install-visual-cpp-for-cross-platform-mobile-development)bakın. iOS kodu oluşturmak için bir Mac bilgisayarınız olması ve diğer gereksinimleri karşılaması gerekir. Ön koşullar ve yükleme yönergeleri listesi için, [iOS kullanarak Oluşturmak için Araçlar Yükle ve Yapılandırmaya](/visualstudio/cross-platform/install-and-configure-tools-to-build-using-ios)bakın. Hedef donanımla eşleşecek x86 veya ARM kodu oluşturabilirsiniz. iOS simülatörü, Android için Microsoft Visual Studio Emülatörü ve bazı Android cihazlar için oluşturmak için x86 yapılandırmalarını kullanın. iOS aygıtları ve çoğu Android aygıt için oluşturmak için ARM yapılandırmalarını kullanın.

\*\*\*Visual Studio 2017 için yükleyiciye C++ iş yükü **yle Linux geliştirmeyi** yükleyebilir ve daha sonra Linux platformlarını hedefleyebilirsiniz. Talimatlar için linux [iş yükünü indir, yükle ve kur'a](../linux/download-install-and-setup-the-linux-development-workload.md)bakın. Bu araç seti, desteklenen herhangi bir mimari için oluşturabilmeniz için yürütülebilir liğinizi hedef makinede derler.

\*\*\*\*ARM64 desteği Visual Studio 2017 ve sonrası için kullanılabilir.

Hedef platform yapılandırmasının nasıl ayarlanılabilenhakkında bilgi için [bkz: Visual C++ Projelerini Hedef 64-Bit, x64 Platformlarına yapılandırın.](../build/how-to-configure-visual-cpp-projects-to-target-64-bit-platforms.md)

## <a name="see-also"></a>Ayrıca bkz.

- [Visual Studio Sürümlerinde Visual C++ Araçları ve Özellikleri](visual-cpp-tools-and-features-in-visual-studio-editions.md)
- [Başlarken](/visualstudio/ide/getting-started-with-cpp-in-visual-studio)
