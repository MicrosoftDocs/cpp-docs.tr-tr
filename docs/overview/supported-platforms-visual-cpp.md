---
title: Desteklenen Platformlar (Visual C++)
ms.date: 12/02/2019
ms.technology: cpp-tools
helpviewer_keywords:
- Visual C++, platforms supported
- platforms [C++]
ms.assetid: 0d893056-4008-411a-b3d1-5f57fd7da95c
ms.openlocfilehash: 049b28d23c7f5f5f023f3b2964577b75992c2998
ms.sourcegitcommit: 5f276064779d90a4cfda758f89e0c0f1e4d1a188
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/09/2020
ms.locfileid: "75793836"
---
# <a name="supported-platforms-visual-c"></a>Desteklenen Platformlar (Visual C++)

Visual Studio kullanılarak oluşturulan uygulamalar, aşağıdaki gibi çeşitli platformları hedefleyebilir.

|İşletim sistemi|x86|X64|ARM|ARM64\*\*\*\*|
|----------------------|---------|---------|---------|---------|
|Windows XP|X\*|X\*|||
|Windows Server 2003|X\*|X\*|||
|Windows Vista|X|X|||
|Windows Server 2008|X|X|||
|Windows 7|X|X|||
|Windows Server 2012 R2|X|X|||
|Windows 8|X|X|X||
|Windows 8.1|X|X|X||
|Windows 10|X|X|X|X|
|Android \*\*|X|X|X|X|
|iOS \*\*|X|X|X|X|
|Linux \*\*\*|X|X|X|X|

\* Windows XP ve Windows Server 2003 projeleri oluşturmak için Visual Studio 2017, Visual Studio 2015, Visual Studio 2013 ve Visual Studio 2012 güncelleştirme 1 ' de bulunan Windows XP platformu araç takımını kullanabilirsiniz. Bu platform araç takımını kullanma hakkında daha fazla bilgi için bkz. [WINDOWS XP Için programları yapılandırma](../build/configuring-programs-for-windows-xp.md). Platform araç takımını değiştirme hakkında daha fazla bilgi için bkz. [nasıl yapılır: hedef Framework ve platform araç takımını değiştirme](../build/how-to-modify-the-target-framework-and-platform-toolset.md).

\*\*, Visual Studio 2017 ve üzeri için yükleyicideki iş yüküyle **Mobil geliştirmeyi C++**  yükleyebilirsiniz. Visual Studio 2015 kurulumu 'nda iOS veya Android platformlarını hedeflemek için isteğe bağlı  **C++ , platformlar arası mobil geliştirme** bileşenini seçin. Yönergeler için bkz. [platformlar arası C++ mobil geliştirme için Visual Install](/visualstudio/cross-platform/install-visual-cpp-for-cross-platform-mobile-development). İOS kodu oluşturmak için bir Mac bilgisayarınız olması ve diğer gereksinimleri karşılamanız gerekir. Önkoşulların ve Yükleme yönergelerinin bir listesi için bkz. [iOS kullanarak derlemek Için araçları yükleme ve yapılandırma](/visualstudio/cross-platform/install-and-configure-tools-to-build-using-ios). Hedef donanımla eşleştirmek için x86 veya ARM kodu oluşturabilirsiniz. İOS simülatörü, Android için Microsoft Visual Studio Öykünücüsü ve bazı Android cihazları için derlemek üzere x86 yapılandırması kullanın. İOS cihazlarını ve Android cihazlarını oluşturmak için ARM yapılandırması kullanın.

\*\*\* Linux platformunu hedeflemek için Visual Studio 2017 ve üzeri yükleyicisindeki iş yüküyle **Linux geliştirmesini C++**  yükleyebilirsiniz. Yönergeler için bkz. [Linux Iş yükünü indirme, yükleme ve kurma](../linux/download-install-and-setup-the-linux-development-workload.md). Bu araç takımı, çalıştırılabilir dosyayı hedef makinede derler, böylece desteklenen herhangi bir mimari için derleyebilirsiniz.

\*\*\*\* ARM64 desteği Visual Studio 2017 ve üzeri sürümlerde kullanılabilir.

Hedef platform yapılandırmasını ayarlama hakkında daha fazla bilgi için bkz. [nasıl yapılır: Visual C++ projelerini yapılandırmak için 64 bit, x64 platformları hedefleyin](../build/how-to-configure-visual-cpp-projects-to-target-64-bit-platforms.md).

## <a name="see-also"></a>Ayrıca bkz.

- [Visual Studio Sürümlerinde Visual C++ Araçları ve Özellikleri](visual-cpp-tools-and-features-in-visual-studio-editions.md)
- [Başlarken](/visualstudio/ide/getting-started-with-cpp-in-visual-studio)
