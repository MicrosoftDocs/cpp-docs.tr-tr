---
title: Visual C++ ActiveX Denetimlerini Yeniden Dağıtma
ms.date: 11/04/2016
helpviewer_keywords:
- controls [C++], redistributing
- controls [C++], distributing
ms.assetid: eefbb7e4-d28c-4c35-98bf-d9540cfaae83
ms.openlocfilehash: 4c7806502024789ed41f3043d7db6c87c7c71ee3
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81359876"
---
# <a name="redistributing-visual-c-activex-controls"></a>Visual C++ ActiveX Denetimlerini Yeniden Dağıtma

Visual C++ 6.0, daha sonra yeniden dağıttığınız uygulamalarda kullanabileceğiniz ActiveX denetimlerini sağlar. Bu denetimler artık Visual C++'a dahil değildir. Visual C++ 6.0 lisans sözleşmelerine göre, Visual C++'da geliştirilen uygulamalarla bu denetimleri yeniden dağıtabilirsiniz.

> [!NOTE]
> Visual C++ 6.0 artık Microsoft tarafından desteklenmiş değildir.

Yeniden dağıtılabilir Visual C++ 6.0 ActiveX denetimlerinin listesi için Visual C++ 6.0 ürün CD'sinin Disk 1'inde Ortak\Redist\Redist.txt bölümüne bakın.

Uygulamaları dağıtırken ActiveX denetimi için .ocx'i yüklemeli ve kaydetmelisiniz (Regsvr32.exe'yi kullanarak). Buna ek olarak, hedef bilgisayarın aşağıdaki sistem dosyalarının geçerli sürümlerine sahip olduğundan emin olmalısınız (yıldız işareti dosyanın kaydedilmesi gerektiğini gösterir):

- Asycfilt.dll

- Comcat.dll\*

- Oleaut32.dll\*

- Olepro32.dll\*

- Stdole2.tlb

Bu DL'ler hedef sistemde yoksa, ilgili işletim sistemini güncelleştirmek için öngörülen mekanizmayı kullanarak bunları güncelleştirmiş olmanız gerekir. Windows işletim sistemleri için en son hizmet [http://windowsupdate.microsoft.com](https://windowsupdate.microsoft.com)paketlerini indirebilirsiniz.

Veritabanına bağlanan bir ActiveX denetimi kullanırken, hedef bilgisayardaki veri kaynağı adını da çoğaltmanız gerekir. Bunu programlı olarak `ConfigDSN`yapabilirsiniz.

Bazı yeniden dağıtılabilir ActiveX denetimleri ek bağımlılıklara sahiptir. Visual C++ 6.0 ürün CD'sindeki Os\System klasöründeki her .ocx dosyası için bir .dep dosyası da vardır. Yeniden dağıtmak istediğiniz her .ocx dosyası için, ilgili .dep dosyasında bir veya daha fazla KULLAN girdisi arayın. Bir dosya listelenmişse, dosyanın hedef bilgisayarda olduğundan emin olmalısınız. .ocx dosyasını doğrudan destekleyen tüm DL'lerin kaydedilmesi gerekir. (Regsvr32.exe'nin başarılı olması için, hedef bilgisayarın öncelikle tüm DL'leri kontrol statik olarak yüklenmiş olarak içermesi gerekir.) Ayrıca, bağımlılık olarak listelenen bir DLL'nin Visual C++ 6.0 CD'deki Os\System klasöründe de .dep dosyası varsa, USES girişleri için .dep dosyasının da araştırılması gerekir.

## <a name="see-also"></a>Ayrıca bkz.

[Visual C++ Dosyalarını Yeniden Dağıtma](redistributing-visual-cpp-files.md)
