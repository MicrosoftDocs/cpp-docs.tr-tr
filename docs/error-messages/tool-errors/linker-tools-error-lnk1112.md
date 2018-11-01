---
title: Bağlayıcı Araçları Hatası LNK1112
ms.date: 11/04/2016
f1_keywords:
- LNK1112
helpviewer_keywords:
- LNK1112
ms.assetid: 425793d8-37e6-4072-9b6e-c3d4e9c12562
ms.openlocfilehash: bc01d56fb8144d23b91c82a7f791a70a5dadb7ef
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50607096"
---
# <a name="linker-tools-error-lnk1112"></a>Bağlayıcı Araçları Hatası LNK1112

> Modül makine türü '*type1*'hedef makine türü ile çakışıyor'*type2*'

## <a name="remarks"></a>Açıklamalar

Girdi olarak belirtilen nesne dosyaları için farklı bir bilgisayara türleri derlendi.

Bağlantı çalışırsanız, örneğin, bir nesne dosyası ile derlenmiş **/CLR** ve bir nesne dosyası ile derlenmiş **/CLR: pure** (makine türü CEE), bağlayıcı hatası LNK1112 oluşturur. **/CLR: pure** derleyici seçeneğini Visual Studio 2015'te kullanım dışı ve Visual Studio 2017'de desteklenmiyor.

Benzer şekilde, x64 ile bir modül oluşturursanız, derleyici ve başka bir modül x86 ile derleyici ve bunları bağlamak için try bağlayıcı LNK1112 oluşturur.

Bu hata için olası neden, 64 bitlik bir uygulama geliştiriyorsanız ancak Visual C++ 64-bit derleyiciler birini yüklemediyseniz ' dir. Bu durumda, 64-bit yapılandırmaları kullanılabilir olmayacak. Bu sorunu düzeltmek için Visual Studio için yükleyiciyi çalıştırın ve eksik C++ bileşenleri yükleyin.

Değiştirirseniz bu hatayı da meydana gelebilir **etkin çözüm yapılandırması** içinde **Configuration Manager** ve Ara proje dosyalarını silmeden önce projeyi oluşturmayı deneyin. Bu hatayı gidermek için seçin **çözümü yeniden derle** gelen **derleme** menüsü. Belirleyebilirsiniz **çözümü Temizle** gelen **derleme** menüsünü ve sonra yapı çözümü.

## <a name="see-also"></a>Ayrıca bkz.

- [Bağlayıcı Araçları Hataları ve Uyarıları](../../error-messages/tool-errors/linker-tools-errors-and-warnings.md)
