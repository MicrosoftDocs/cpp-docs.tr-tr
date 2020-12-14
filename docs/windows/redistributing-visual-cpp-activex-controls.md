---
description: 'Daha fazla bilgi edinin: Visual C++ ActiveX denetimlerini yeniden dağıtma'
title: Visual C++ ActiveX Denetimlerini Yeniden Dağıtma
ms.date: 11/04/2016
helpviewer_keywords:
- controls [C++], redistributing
- controls [C++], distributing
ms.assetid: eefbb7e4-d28c-4c35-98bf-d9540cfaae83
ms.openlocfilehash: 4960af93b140e883ff50f6ff81824cd9e67d44f6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97247351"
---
# <a name="redistributing-visual-c-activex-controls"></a>Visual C++ ActiveX Denetimlerini Yeniden Dağıtma

Visual C++ 6,0, daha sonra yeniden dağıtacağınız uygulamalarda kullanabileceğiniz ActiveX denetimleri sağlar. Bu denetimler artık Visual C++ dahil değildir. Visual C++ 6,0 lisans sözleşmeleri uyarınca, bu denetimleri Visual C++ geliştirilmiş uygulamalarla yeniden dağıtabilirsiniz.

> [!NOTE]
> Visual C++ 6,0 artık Microsoft tarafından desteklenmemektedir.

Yeniden dağıtılabilir Visual C++ 6,0 ActiveX denetimlerinin listesi için Visual C++ 6,0 ürün CD 'sindeki disk 1 ' de Common\Redist\Redist.txt bakın.

Uygulamaları dağıtırken, ActiveX denetimi için. ocx ' i yüklemeli ve kaydetmeniz gerekir (Regsvr32.exe kullanarak). Ayrıca, hedef bilgisayarın aşağıdaki sistem dosyalarının güncel sürümlerine sahip olduğundan emin olun (bir yıldız işareti dosyanın kaydedilmesi gerektiğini gösterir):

- Asycfilt.dll

- Comcat.dll \*

- Oleaut32.dll \*

- Olepro32.dll \*

- Stdole2. tlb

Bu dll 'Ler hedef sistemde kullanılabilir değilse, bunlara karşılık gelen işletim sistemini güncelleştirmek için önceden belirlenmiş mekanizmayı kullanarak bunları güncelleştirirsiniz. Windows işletim sistemleri için en son hizmet paketlerini ' den indirebilirsiniz [http://windowsupdate.microsoft.com](https://windowsupdate.microsoft.com) .

Veritabanına bağlanan bir ActiveX denetimi kullanırken, hedef bilgisayardaki veri kaynağı adını da çoğaltmanız gerekir. Bunu, gibi işlevlerle programlama yoluyla yapabilirsiniz `ConfigDSN` .

Bazı yeniden dağıtılabilir ActiveX denetimleri ek bağımlılıklara sahiptir. Visual C++ 6,0 ürün CD 'sindeki Os\System klasöründeki her. ocx dosyası için de bir. dep dosyası vardır. Yeniden dağıtmak istediğiniz her. ocx dosyası için, karşılık gelen. DEP dosyasında bir veya daha fazla giriş KULLANıR. Bir dosya listeleniyorsa, dosyanın hedef bilgisayarda olduğundan emin olmanız gerekir. Doğrudan bir. ocx dosyasını destekleyen dll 'Lerin kaydedilmesi gerekir. (Regsvr32.exe başarılı olması için, hedef bilgisayarın öncelikle denetimin statik olarak yüklediği tüm dll 'Leri içermesi gerekir.) Ayrıca, bağımlılık olarak listelenen bir DLL 'nin Ayrıca Visual C++ 6,0 CD 'sindeki Os\System klasöründe bir. dep dosyası varsa, bu. DEP dosyasında de girdileri KULLANıR.

## <a name="see-also"></a>Ayrıca bkz.

[Visual C++ Dosyalarını Yeniden Dağıtma](redistributing-visual-cpp-files.md)
