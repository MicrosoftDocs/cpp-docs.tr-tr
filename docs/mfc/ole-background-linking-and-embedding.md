---
title: 'OLE arka planı: Bağlama ve katıştırma'
ms.date: 11/04/2016
helpviewer_keywords:
- OLE embedded items [MFC]
- item types [MFC], defined
- item types [MFC]
- OLE [MFC], linked items
- linked items (OLE) [MFC]
- embedded objects [MFC]
- OLE items [MFC], types
ms.assetid: 11107711-eb96-4099-8f5c-7910bb3ecb75
ms.openlocfilehash: 02607df2a8fa086c5751f2b446e349a3efdbcd20
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62186808"
---
# <a name="ole-background-linking-and-embedding"></a>OLE arka planı: Bağlama ve katıştırma

Bir kapsayıcı uygulamasında Paste komutu kullanarak, bir katıştırılmış bileşen veya gömülü bir öğe oluşturabilirsiniz. Gömülü bir öğe için kaynak verilerini içerdiği OLE belgesi bir parçası olarak depolanır. Bu şekilde, dosyanın bir sözcük işlemcisi belge için metin içerebilir ve bit eşlemler, grafikler, formülleri veya herhangi bir veri türünü de içerebilir.

OLE başka bir uygulamadan verileri birleştirmek için başka bir yol sağlar: bağlı bir bileşen veya bağlantılı öğe veya bağlantı oluşturma. Paste komutu yerine Yapıştır komutunu dışında bağlantılı bir öğe oluşturma adımlarını gömülü bir öğe oluşturmaya benzerdir. Katıştırılmış bir bileşen farklı olarak, genellikle ayrı bir dosyada olan özgün veri yoluna bağlı bir bileşen depolar.

Örneğin, bir sözcük işlemcisi belge çalışıyorsanız ve bazı elektronik hücrelere bağlantılı bir öğe oluşturun, bağlantılı öğe için veriler özgün elektronik belge depolanır. Sözcük işlemcisi belgeyi yalnızca öğesi, diğer bir deyişle, özgün elektronik belge bağlantısını içeren bulunabileceği belirten bilgileri içerir. Hücreleri çift tıkladığınızda, elektronik tablo uygulama başlatılır ve özgün elektronik belge depolandığı gelen yüklenir.

Tüm OLE öğesini gömülü veya bağlantılı, oluşturduğu uygulamaya göre ilişkili bir türü vardır. Örneğin, bir Microsoft Paintbrush öğe bir türde öğe ve bir Microsoft Excel öğesi başka bir türdür. Bazı uygulamalar, ancak birden fazla öğe türü oluşturabilirsiniz. Örneğin, Microsoft Excel çalışma öğeleri ve grafik öğeleri makro sayfası öğeleri oluşturabilirsiniz. Bu öğelerin her biri bir sınıf tanımlayıcısını kullanarak sistem tarafından benzersiz şekilde tanımlanabilir veya **CLSID**.

## <a name="see-also"></a>Ayrıca bkz.

[OLE Arka Planı](../mfc/ole-background.md)<br/>
[OLE arka planı: Kapsayıcılar ve sunucular](../mfc/ole-background-containers-and-servers.md)<br/>
[Kapsayıcılar: İstemci öğeleri](../mfc/containers-client-items.md)<br/>
[Sunucular: Sunucu öğeleri](../mfc/servers-server-items.md)
