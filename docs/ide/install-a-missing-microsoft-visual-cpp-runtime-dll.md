---
title: "Eksik Microsoft Visual C++ çalışma zamanı DLL yükleme | Microsoft Docs"
description: "Nasıl bulmak ve Visual C++ çalışma zamanı DLL'leri eksik yükleyin."
ms.date: 03/13/2018
ms.topic: article
dev_langs:
- C++
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 6410c9753577852989172121d01c9d768f5373b3
ms.sourcegitcommit: 9239c52c05e5cd19b6a72005372179587a47a8e4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/16/2018
---
# <a name="install-a-missing-microsoft-visual-c-runtime-dll"></a>Eksik Microsoft Visual C++ çalışma zamanı DLL yükleme

Microsoft Visual C++ genellikle kullanılarak yazılmış programları bazı ek Visual C++ çalışma zamanı kitaplığı dosyaları ya da çalıştırmak için DLL'leri gerektirir. Bu çalışma zamanı DLL'leri kullanılabilir olan bir *yeniden dağıtılabilir paketi*, her sürümü Visual C++ Kitaplık dosya yükleyici programı. Herhangi bir program tarafından gerekli yeniden dağıtılabilir paketi yükleyicisi tarafından bulunması gerekir. Değilse, bazen bir yeniden dağıtılabilir paketi kendiniz yükleyebilir ve programını çalıştırdığınızda, bir sistem hatası düzeltin.

Bir şey diyor programı başlattığınızda bir sistem hatası alırsanız, bir program bir Visual C++ çalışma zamanı DLL eksik olduğunu anlayabilirsiniz "tetiklenen, VCRuntime140.dll bilgisayarınızdan eksik olduğundan program başlatılamıyor"gibi. Genellikle, bu sorunu programı kaldırmanın, ardından yeniden yüklemeyi düzeltilebilir. Diğer olası giderir önce ilk olarak, bu adımı çalışırken önerilir.

Bazen bir program tarafından yüklenen yeniden dağıtılabilir paketi güncel değil. Microsoft çalışma zamanı DLL'leri güncelleştirilmiş sürümlerini zaman zaman, adres hataları ve güvenlik sorunları için kullanılabilmesini sağlar. Bilgisayarınızı güvenli ve düzgün çalışır durumda tutmak için en son güncelleştirmeyi tüm çalışma zamanı DLL için kullanmak iyi bir fikirdir. Bu güncelleştirme, sizin için sağlayabilir programınızın kullanılabilir güncelleştirilmiş bir yükleyici olup olmadığını denetleyin. Varsa, güncelleştirilmiş bir yükleyici programı yeniden kullanın.

Programı yeniden yüklemeyi azalttıktan sistem hatası yapmaz, ardından program yükleyici bozuk bozulmuş veya olabilir veya bilgisayarınızda çalışma zamanı DLL'leri bozuk olabilir. Deneyin yükleyici programınız için yeni bir kopyasını indirin ve ilk yeniden yüklemek için kullanın. Ardından bu işe yaramazsa ya da bir yükleyici kullanılamıyor, bilgisayarınızda Microsoft Visual C++ yeniden dağıtılabilir yüklemeleri denetlemek için faydalı olabilir.

Bu tablo bir veya daha fazla yeniden dağıtılabilir paketlerini, yeniden dağıtılabilir paketi bir kopyasını indirmek için bağlantılar ile birlikte dahil edilen DLL'lerin bir listesini gösterir. Yeniden dağıtılabilir paketi yeni bir kopyasını indirmeden önce var olan bir yüklemesini onarmak görmeniz gerekir.

|DLL eksik  |Yeniden dağıtılabilir paketi  |
|---------|---------|
|atl80.dll<br />msvcm80.dll<br />msvcp80.dll<br />msvcr80.dll<br />mfc80.dll<br />mfc80u.dll<br />mfcm80.dll<br />mfcm80u.dll|[Microsoft Visual C++ 2005 yeniden dağıtılabilir (x86)](https://www.microsoft.com/en-us/download/details.aspx?id=5638)<br />[Microsoft Visual C++ 2005 yeniden dağıtılabilir paketi (x64)](https://www.microsoft.com/en-us/download/details.aspx?id=18471)<br />[Microsoft Visual C++ 2005 Service Pack 1 Redistributable Package MFC güvenlik güncelleştirmesi](https://www.microsoft.com/en-us/download/details.aspx?id=26347)|
|atl90.dll<br />msvcr90.dll<br />msvcm90.dll<br />msvcp90.dll<br />mfc90.dll<br />mfc90u.dll<br />mfcmifc80.dll<br />mfcm90.dll<br />mfcm90u.dll|[Microsoft Visual C++ 2008 yeniden dağıtılabilir - x86](https://www.microsoft.com/en-us/download/details.aspx?id=5582)<br />[Microsoft Visual C++ 2008 yeniden dağıtılabilir - x64](https://www.microsoft.com/en-us/download/details.aspx?id=2092)<br />[Microsoft Visual C++ 2008 Service Pack 1 Redistributable Package MFC güvenlik güncelleştirmesi](https://www.microsoft.com/en-us/download/details.aspx?id=26368)|
|atl100.dll<br />msvcr100.dll<br />msvcp100.dll<br />msdia71.dll<br />vcomp100.dll<br />mfc100.dll<br />mfc100u.dll<br />mfcmifc80.dll<br />mfcm100.dll<br />mfcm100u.dll|[Microsoft Visual C++ 2010 x86 yeniden dağıtılabilir](https://www.microsoft.com/en-us/download/details.aspx?id=8328)<br />[Microsoft Visual C++ 2010 x64 yeniden dağıtılabilir](https://www.microsoft.com/en-us/download/details.aspx?id=13523)<br />[Microsoft Visual C++ 2010 Service Pack 1 Redistributable Package MFC güvenlik güncelleştirmesi](https://www.microsoft.com/en-us/download/details.aspx?id=26999)|
|atl110.dll<br />msvcr110.dll<br />msvcp110.dll<br />mfc110.dll<br />mfc110u.dll<br />mfcmifc80.dll<br />mfcm110.dll<br />mfcm110u.dll<br />concrt110.dll<br />vccorlib110.dll<br />vcamp110.dll<br />vcomp110.dll|[Microsoft Visual C++ 2012 Redistributable (Visual Studio 2012 güncelleştirmesi 4)](https://www.microsoft.com/en-us/download/details.aspx?id=30679)|
|msvcr120.dll<br />msvcp120.dll<br />mfc120.dll<br />mfc120u.dll<br />mfcmifc80.dll<br />mfcm120.dll<br />mfcm120u.dll<br />concrt120.dll<br />vccorlib120.dll<br />vcamp120.dll<br />vcomp120.dll|[Microsoft Visual C++ 2013 yeniden dağıtılabilir (karşıdan yüklemelere tek tek bağlantıları)](https://support.microsoft.com/en-us/help/3179560/update-for-visual-c-2013-and-visual-c-redistributable-package)<br />[Visual Studio 2013 için birden çok baytlı MFC Kitaplığı](https://www.microsoft.com/en-us/download/details.aspx?id=40770)<br />[Dışarıdan yüklenen Windows 8.1 uygulamaları (.zip indirme) için Visual C++ 2013 çalışma zamanı](http://download.microsoft.com/download/5/F/0/5F0F8404-9329-44A9-8176-ED6F7F746F25/VCLibs_Redist_Packages.zip)|
|vcruntime140.dll<br />vcruntime140_app.dll<br />msvcp140.dll<br />msvcp140_1.dll, etc.<br />mfc140.dll<br />mfc140u.dll<br />mfcmifc80.dll<br />mfcm140.dll<br />mfcm140u.dll<br />concrt140.dll<br />vccorlib140.dll<br />vcamp140.dll<br />vcomp140.dll|[Microsoft Visual C++ 2017 yeniden dağıtılabilir (x86)](https://go.microsoft.com/fwlink/?LinkId=746571)<br />[Microsoft Visual C++ 2017 yeniden dağıtılabilir (x64)](https://go.microsoft.com/fwlink/?LinkId=746572)|
|msvcr100_clr0400.dll<br />msvcr110_clr0400.dll<br />msvcr120_clr0400.dll|[.NET Framework indirin](https://www.microsoft.com/net/download/framework)|

### <a name="to-repair-an-existing-redistributable-package"></a>Var olan yeniden dağıtılabilir paketini onarmak için

1. Denetim Masası'nı açın. Windows 10'da girin *Denetim Masası* masaüstü görev çubuğuna denetim arayın ve ardından seçin **Denetim Masası** seçeneklerden.

2. Denetim Masası'nda seçin **programları** > **programlar ve Özellikler**. Microsoft Visual C++ eksik DLL karşılık gelen yeniden dağıtılabilir sürümünü seçin. Varsa bir **değişiklik** düğmesi listesinin başında görünüp seçin. Tek seçim ise **kaldırma**, bu yeniden dağıtılabilir paketi sürümü onarılamıyor.

3. Seçin **onarım** yeniden dağıtılabilir paketi için Kurulum iletişim kutusunda. Onarım işlemi tamamlandığında yeniden başlatmanız gerekebilir.