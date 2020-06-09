---
title: 'OLE Arka Planı: Bağlama ve Katıştırma'
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
ms.openlocfilehash: 6b6032d2e772728495d4ddb1dbfaa5daf7348b60
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84619882"
---
# <a name="ole-background-linking-and-embedding"></a>OLE Arka Planı: Bağlama ve Katıştırma

Bir kapsayıcı uygulamasında Yapıştır komutunun kullanılması katıştırılmış bir bileşen veya katıştırılmış öğe oluşturabilir. Katıştırılmış bir öğenin kaynak verileri, kendisini içeren OLE belgesinin bir parçası olarak depolanır. Bu şekilde, Word işlemci belgesi için bir belge dosyası metin içerebilir ve ayrıca bit eşlemler, grafikler, formüller veya diğer veri türlerini içerebilir.

OLE başka bir uygulamadan veri eklemenin başka bir yolunu sağlar: bağlantılı bir bileşen ya da bağlantılı öğe veya bağlantı oluşturma. Bağlantılı öğe oluşturma adımları, katıştırılmış bir öğe oluşturma ile benzerdir, ancak Paste komutu yerine Paste link komutunu kullanmanız gerekir. Katıştırılmış bir bileşenden farklı olarak, bağlantılı bir bileşen orijinal verilerin bir yolunu depolar ve bu genellikle ayrı bir dosyadır.

Örneğin, bir sözcük işlemci belgesinde çalışıyorsanız ve bazı elektronik tablo hücrelerine bağlantılı öğe oluşturursanız, bağlantılı öğe için veriler özgün elektronik tablo belgesinde depolanır. Sözcük işlemci belgesi yalnızca öğenin nerede bulunilebileceği, yani özgün elektronik tablo belgesinin bağlantısını içeren bilgileri içerir. Hücrelere çift tıkladığınızda, elektronik tablo uygulaması başlatılır ve özgün elektronik tablo belgesi, depolandıkları yerden yüklenir.

Katıştırılmış veya bağlı olduğu her OLE öğesi, kendisini oluşturan uygulamaya göre onunla ilişkilendirilmiş bir türe sahiptir. Örneğin, bir Microsoft Paintbrush öğesi bir tür öğe, Microsoft Excel öğesi ise başka bir türdür. Ancak bazı uygulamalar, birden fazla öğe türü oluşturabilir. Örneğin, Microsoft Excel çalışma sayfası öğeleri, grafik öğeleri ve makro sayfası öğeleri oluşturabilir. Bu öğelerin her biri sistem tarafından, bir sınıf tanımlayıcısı veya **CLSID**kullanılarak benzersiz şekilde tanımlanabilir.

## <a name="see-also"></a>Ayrıca bkz.

[OLE arka planı](ole-background.md)<br/>
[OLE Arka Planı: Kapsayıcılar ve Sunucular](ole-background-containers-and-servers.md)<br/>
[Kapsayıcılar: İstemci Öğeleri](containers-client-items.md)<br/>
[Sunucular: Sunucu Öğeleri](servers-server-items.md)
