---
title: Yürütülebilir Hata Ayıklamayı Çalıştırmak için Test Makinesi Hazırlama
ms.date: 07/02/2019
helpviewer_keywords:
- debug executable, preparing a test machine to run
ms.assetid: f0400989-cc2e-4dce-9788-6bdbe91c6f5a
ms.openlocfilehash: 26a92d5efc4bf9f0332a0e81fa2f9c8b2c2a958f
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81359918"
---
# <a name="preparing-a-test-machine-to-run-a-debug-executable"></a>Yürütülebilir Hata Ayıklamayı Çalıştırmak için Test Makinesi Hazırlama

Visual C++ ile oluşturulmuş bir uygulamanın hata ayıklama sürümünü sınamak için bir bilgisayar hazırlamak için, uygulamanın bağlı olduğu Visual C++ kitaplık DL'lerinin hata ayıklama sürümlerini dağıtmanız gerekir. Hangi DL'lerin dağıtılması gerektiğini belirlemek için, [Visual C++ Uygulamasının Bağımlılıklarını Anlama'daki](understanding-the-dependencies-of-a-visual-cpp-application.md)adımları izleyin. Genellikle, Visual C++ kitaplık DL'lerinin hata ayıklama sürümlerinde "d" ile biten adlar bulunur; örneğin, msvcr100.dll hata ayıklama sürümü msvcr100d.dll olarak adlandırılır.

> [!NOTE]
> Bir uygulamanın hata ayıklama sürümleri yeniden dağıtılamaz ve Visual C++ kitaplık DLL'lerinin hata ayıklama sürümleri yeniden dağıtılamaz. Uygulamaların hata ayıklama sürümlerini ve Visual C++ DLL'lerini yalnızca diğer bilgisayarlarınıza dağıtabilir, tek amacı hata ayıklamak ve uygulamaları Visual Studio yüklü olmayan bir bilgisayarda test etmek. Daha fazla bilgi için [bkz.](redistributing-visual-cpp-files.md)

Visual C++ kitaplık DL'lerinin hata ayıklama sürümlerini bir uygulamanın hata ayıklama sürümüyle birlikte dağıtmanın üç yolu vardır.

- Doğru kitaplık sürümü ve uygulamanızın mimarisi için birleştirme modülleri içeren bir Kurulum projesi kullanarak belirli bir Visual C++ DLL'nin hata ayıklama sürümünü %windir%\system32\ dizinine yüklemek için merkezi dağıtımı kullanın. Birleştirme modülleri \Ortak Dosyalar\Birleştirme Modülleri'ndeki\\Program Dosyaları veya Program Dosyaları (x86) dizininde bulunur. Birleştirme modülünün hata ayıklama sürümünde hata ayıklama örneğin Microsoft_VC110_DebugCRT_x86.msm adı vardır. Bu dağıtımın bir örneği [Walkthrough: Visual C++ Uygulamasını Kurulum Projesi Kullanarak Dağıtma'da](walkthrough-deploying-a-visual-cpp-application-by-using-a-setup-project.md)bulunabilir.

- \Microsoft Visual Studio sürümünde Program Dosyaları veya Program Dosyaları (x86) dizininde sağlanan dosyaları kullanarak uygulamanın yükleme dizininde belirli bir Visual C++ DLL'nin hata ayıklama sürümünü yüklemek için yerel dağıtımı kullanın>\Microsoft Visual Studio \<sürümünde\VC\redist\Debug_NonRedist\\.

    > [!NOTE]
    >  Visual Studio 2005 veya Visual Studio 2008 kullanarak başka bir bilgisayarda oluşturulmuş uygulamanızın uzaktan hata ayıklama için, Visual C++ kitaplık DLs'lerin hata ayıklama sürümlerini paylaşılan yan yana derlemeler olarak dağıtmanız gerekir. İlgili birleştirme modüllerini yüklemek için bir Kurulum projesi veya Windows Yükleyici kullanabilirsiniz.

- Proje çıktısını ve diğer dosyaları uzak bilgisayara kopyalamak için Visual Studio'daki **Configuration Manager** iletişim kutusunda the_**Dağıt** seçeneğini kullanın.

Visual C++ DL'ler yüklendikten sonra, ağ paylaşımında uzaktan hata ayıklama çalıştırabilirsiniz. Uzaktan hata ayıklama hakkında daha fazla bilgi için [Uzaktan Hata Ayıklama](/visualstudio/debugger/remote-debugging)bölümüne bakın.

## <a name="see-also"></a>Ayrıca bkz.

[Visual C++ üzerinde Dağıtım](deployment-in-visual-cpp.md)<br>
[Windows Installer Komut satırı seçenekleri](/windows/win32/Msi/command-line-options)<br>
[Dağıtım Örnekleri](deployment-examples.md)<br>
[Uzaktan Hata Ayıklama](/visualstudio/debugger/remote-debugging)
