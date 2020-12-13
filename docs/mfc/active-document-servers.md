---
description: 'Daha fazla bilgi edinin: etkin belge sunucuları'
title: Etkin Belge Sunucuları
ms.date: 11/04/2016
helpviewer_keywords:
- active documents [MFC], servers
- servers [MFC], active document
- active document servers [MFC]
ms.assetid: 131fec1e-02a0-4305-a7ab-903b911232a7
ms.openlocfilehash: 37a8e74b0c4b1b37bb031db522bed394c2a9d545
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97150325"
---
# <a name="active-document-servers"></a>Etkin Belge Sunucuları

Word, Excel veya PowerPoint gibi etkin belge sunucuları, etkin belgeler olarak adlandırılan diğer uygulama türlerinin belgelerini barındırır. OLE Embedded nesnelerinin aksine (yalnızca başka bir belge sayfası içinde görüntülenen), etkin belgeler, tam arabirimi ve bunları oluşturan sunucu uygulamasının tüm yerel işlevlerini sağlar. Kullanıcılar, sık kullanılan uygulamalarının tam gücünden yararlanarak belge oluşturabilir (etkin belge etkinse), ancak sonuçta elde edilen projeyi tek bir varlık olarak işleyebilirler.

Etkin belgelerde birden fazla sayfa bulunabilir ve her zaman yerinde etkin bulunur. Etkin belgeler, kendi menülerini, kapsayıcının **Dosya** ve **Yardım** menüleriyle birleştirerek kullanıcı arabiriminin bir bölümünü denetler. Kapsayıcının düzenleme alanının tamamını kaplar ve görünümleri ve yazıcı sayfasının yerleşimini (kenar boşlukları, altbilgiler, vb.) denetler.

MFC, belge/görünüm arabirimleri, komut gönderme haritaları, yazdırma, menü yönetimi ve kayıt defteri yönetimi ile etkin belge sunucuları uygular. Belirli programlama gereksinimleri, [etkin belgelerde](active-documents.md)ele alınmıştır.

MFC [CDocObjectServer](reference/cdocobjectserver-class.md) sınıfı ile etkin belgeleri destekler, [CCmdTarget](reference/ccmdtarget-class.md)ve [CDocObjectServerItem](reference/cdocobjectserveritem-class.md)öğesinden türetilir, [coleserveröğesinden](reference/coleserveritem-class.md)türetilir. MFC Colet [Clienentidıtem](reference/coleclientitem-class.md)öğesinden türetilmiş [Copadocobjectıtem](reference/coledocobjectitem-class.md) sınıfıyla etkin belge kapsayıcılarını destekler.

`CDocObjectServer` etkin belge arabirimlerini eşleştirir ve etkin bir belgeyi başlatır ve etkinleştirir. MFC Ayrıca, ETKIN belgelerde komut yönlendirmeyi işlemek için makrolar sağlar. Uygulamanızdaki etkin belgeleri kullanmak için Stffx. h dosyanıza AfxDocOb. h ekleyin.

Normal MFC sunucusu kendi kendine `COleServerItem` türetilmiş sınıfını takar. Uygulama sunucunuza Birleşik belge desteğini sağlamak için **mini sunucu** veya **tam sunucu** onay kutusunu seçerseniz, MFC Uygulama Sihirbazı sizin için bu sınıfı oluşturur. **Etkin belge sunucusu** onay kutusunu da SEÇERSENIZ, MFC Uygulama Sihirbazı bunun yerine öğesinden türetilmiş bir sınıf oluşturur `CDocObjectServerItem` .

`COleDocObjectItem`Sınıfı, OLE kapsayıcısının etkin bir belge kapsayıcısı olmasına olanak sağlar. MFC Uygulama Sihirbazı 'nın Birleşik belge desteği sayfasında **etkin belge kapsayıcısı** onay kutusunu seçerek etkin bir belge kapsayıcısı oluşturmak Için MFC Uygulama Sihirbazı ' nı kullanabilirsiniz. Daha fazla bilgi için bkz. [etkin bir belge kapsayıcı uygulaması oluşturma](creating-an-active-document-container-application.md).

## <a name="see-also"></a>Ayrıca bkz.

[Etkin belge kapsama](active-document-containment.md)
