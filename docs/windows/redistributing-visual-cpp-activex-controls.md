---
title: Visual C++ ActiveX Denetimlerini Yeniden Dağıtma
ms.date: 11/04/2016
helpviewer_keywords:
- controls [C++], redistributing
- controls [C++], distributing
ms.assetid: eefbb7e4-d28c-4c35-98bf-d9540cfaae83
ms.openlocfilehash: e8eba02f1a2c5706a91b85e3b20a4e4be557537b
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/01/2019
ms.locfileid: "58787794"
---
# <a name="redistributing-visual-c-activex-controls"></a>Visual C++ ActiveX Denetimlerini Yeniden Dağıtma

Visual C++ 6.0, ardından yeniden dağıtmak uygulamalarında kullanabileceğiniz ActiveX denetimleri sağlar. Bu denetimler, artık Visual C++'da dahil edilir. Visual C++ 6.0 için lisans sözleşmelerine göre Visual C++'da geliştirilmiş uygulamaları ile bu denetimleri yeniden dağıtabilirsiniz.

> [!NOTE]
>  Visual C++ 6.0, artık Microsoft tarafından desteklenir.

Yeniden dağıtılabilir Visual C++ 6.0 ActiveX denetimleri listesi için Visual C++ 6.0 ürün CD'sinin disk 1 üzerinde Common\Redist\Redist.txt bakın.

Uygulamaları dağıtırken, yükleyin ve .ocx (Regsvr32.exe kullanarak) bir ActiveX denetimi için kaydolun. Ayrıca, hedef bilgisayarın (yıldız işareti, dosyanın kaydedilmesi gerekiyor gösterir) aşağıdaki sistem dosyalarının güncel sürümlerini olduğundan emin olmanız gerekir:

- Asycfilt.dll

- Comcat.dll \*

- Oleaut32.dll \*

- Olepro32.dll \*

- Stdole2.tlb

Bu DLL'leri hedef sistemde mevcut değilse bunları karşılık gelen işletim sistemini güncelleştirmek için öngörülen mekanizmasını kullanarak güncel almanız gerekir. Windows işletim sistemlerinde en son hizmet paketleri indirebileceğiniz [ http://windowsupdate.microsoft.com ](https://windowsupdate.microsoft.com).

Bir veritabanına bağlanan bir ActiveX denetimini kullanırken aynı zamanda veri kaynağı adı hedef bilgisayarda çoğaltmak gerekir. Program aracılığıyla işlevleriyle gibi bunu yapabilirsiniz `ConfigDSN`.

Yeniden dağıtılabilir bazı ActiveX denetimleri, ek bağımlılıklara sahip. Her .ocx dosya için Os\System klasöründe Visual C++ 6.0 ürün CD'sinin de bir.DEP dosyası mevcuttur. Yeniden dağıtmak istediğiniz her .ocx dosya için karşılık gelen .dep dosyasındaki bir veya daha fazla KULLANIMLAR girdileri arayın. Bir dosya listeleniyorsa, dosyanın hedef bilgisayarda olduğundan emin olmanız gerekir. DLL'lerin doğrudan destekleyen bir .ocx dosyasının kaydedilmesi gerekir. (Başarılı olması Regsvr32.exe için hedef bilgisayarı ilk tüm denetim statik olarak DLL'leri içermelidir.) Ayrıca, bir bağımlılık olarak listelenen bir DLL de bir.DEP dosyası Visual C++ 6.0 CD Os\System klasöründe varsa, bu .dep dosyasında kullandığı girişler için de araştırmanız gerekir.

## <a name="see-also"></a>Ayrıca bkz.

[Visual C++ Dosyalarını Yeniden Dağıtma](redistributing-visual-cpp-files.md)