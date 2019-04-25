---
title: Sunucular
ms.date: 11/04/2016
helpviewer_keywords:
- OLE server applications [MFC]
- OLE server applications [MFC], activation
- full-server
- servers
- mini-server
- OLE server applications [MFC], server types
- server applications [MFC]
ms.assetid: e45172e8-eae3-400a-8139-0fa009a42fdc
ms.openlocfilehash: 7b1eb0df439bcfde3aa295f23a90291e865df3a9
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62307841"
---
# <a name="servers"></a>Sunucular

OLE öğeleri (veya bileşenleri) kullanmak için bir sunucu uygulaması (veya uygulama bileşeni) kapsayıcı uygulamalar tarafından oluşturur. Görsel düzenleme sunucu uygulaması, görsel düzenleme veya yerinde etkinleştirmeyi de destekler. OLE server'ın başka bir formu bir [Otomasyon sunucusu](../mfc/automation-servers.md). Bazı sunucu uygulamaları, yalnızca katıştırılmış öğeler oluşturulmasını destekler; Başkalarının katıştırılmış ve bağlantılı öğeler oluşturulmasını destekler. Bu ender olsa bazı yalnızca bağlamayı destekler. Kullanıcı bir öğeyi düzenlemek istediğinde tüm sunucu uygulamaları, kapsayıcı uygulamalar tarafından etkinleştirme desteklemelidir. Bir uygulama bir kapsayıcı hem bir sunucu olabilir. Diğer bir deyişle, bu her ikisi de kendi belgelerine verileri birleştirmek ve oluşturabilirsiniz diğer uygulamaları belgelerine öğeleri olarak dahil edilebilir veri.

Bir miniserver, yalnızca bir kapsayıcı tarafından başlatılabilen sunucu uygulaması özel türüdür. Microsoft Draw ve Microsoft Graph miniservers örnekleridir. Bir miniserver diskteki dosyaları olarak belgeleri depolamaz. Bunun yerine, kendi belgelerini okur ve kapsayıcılarına ait öğeler için yazar. Sonuç olarak, bir miniserver, bağlama değil yalnızca ekleme destekler.

Tam sunucu, tek başına bir uygulama olarak çalıştırın veya bir kapsayıcı uygulama tarafından başlatılan. Tam sunucu belgeleri, diskteki dosyaları olarak depolayabilirsiniz. Yalnızca her iki katıştırma ekleme ve bağlama veya yalnızca bağlama destekleyebilir. Bir kapsayıcı uygulamasının kullanıcı, sunucu ve Yapıştır komut kapsayıcısında Kes veya Kopyala komutunu seçerek gömülü bir öğe oluşturabilirsiniz. Kopyalama komutu sunucusundaki ve Yapıştır komut kapsayıcısında seçerek bağlantılı bir öğe oluşturulur. Alternatif olarak, kullanıcı bir gömülü veya bağlantılı öğe Nesne Ekle iletişim kutusunu kullanarak oluşturabilirsiniz.

Sunucuları farklı türlerdeki özellikler aşağıdaki tabloda özetlenmiştir:

### <a name="server-characteristics"></a>Sunucu Özellikleri

|Sunucu türü|Birden çok örneği destekler|Belge başına öğe sayısı|Örnek başına belgeleri|
|--------------------|---------------------------------|------------------------|----------------------------|
|Miniserver|Evet|1.|1.|
|SDI tam sunucu|Evet|1 (bağlama destekleniyorsa, 1 veya daha fazla)|1.|
|MDI tam sunucu|Hayır (gerekli değildir)|1 (bağlama destekleniyorsa, 1 veya daha fazla)|0 veya daha fazla|

Birden fazla kapsayıcı bir gömülü veya bağlantılı öğeyi düzenlemek için kullanılan olay, bir sunucu uygulaması aynı anda birden çok kapsayıcı desteklemelidir. Sunucu bir SDI uygulaması (veya bir iletişim kutusu arabirimi ile bir miniserver) ise, birden fazla sunucunun aynı anda çalıştırabilirsiniz olması gerekir. Bu, uygulamanın her bir kapsayıcı isteği işlemek için ayrı bir örneğini sağlar.

Sunucu bir MDI uygulaması ise, bir öğeyi düzenlemek için bir kapsayıcı her durumda yeni bir MDI alt penceresi oluşturabilirsiniz. Bu şekilde, birden çok kapsayıcı uygulamanın tek bir örneğini destekler.

Sunucu uygulamasının OLE sistem DLL'lerini başka bir kapsayıcı hizmetlerinin istediğinde sunucunun bir örneği zaten çalışıyorsa yapmanız gerekenler bildirmeniz gerekir: olup sunucunun yeni bir örneğini başlatmak veya bir örneğinin tüm kapsayıcıları istekleri Sunucu.

Sunucuları hakkında daha fazla bilgi için bkz:

- [Sunucular: Sunucu uygulama](../mfc/servers-implementing-a-server.md)

- [Sunucular: Sunucu belgeleri uygulama](../mfc/servers-implementing-server-documents.md)

- [Sunucular: Yerinde çerçeve Windows uygulama](../mfc/servers-implementing-in-place-frame-windows.md)

- [Sunucular: Sunucu öğeleri](../mfc/servers-server-items.md)

- [Sunucular: Kullanıcı arabirimi sorunları](../mfc/servers-user-interface-issues.md)

## <a name="see-also"></a>Ayrıca bkz.

[OLE](../mfc/ole-in-mfc.md)<br/>
[Kapsayıcılar](../mfc/containers.md)<br/>
[Kapsayıcılar: Gelişmiş Özellikler](../mfc/containers-advanced-features.md)<br/>
[Menüler ve Kaynaklar (OLE)](../mfc/menus-and-resources-ole.md)<br/>
[Kayıt](../mfc/registration.md)<br/>
[Otomasyon Sunucuları](../mfc/automation-servers.md)
