---
title: Standart Komut ve Pencere Kimlikleri
ms.date: 11/04/2016
helpviewer_keywords:
- standard command and Window IDs
ms.assetid: 0424805c-fff8-4531-8f0c-15cfb13aa612
ms.openlocfilehash: a7f9e37702c686e13379d4034be94949f92e5e79
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372953"
---
# <a name="standard-command-and-window-ids"></a>Standart Komut ve Pencere Kimlikleri

Microsoft Hazırlık Sınıf Kitaplığı, Afxres.h'deki bir dizi standart komut ve pencere dislerini tanımlar. Bu işlevler en sık kaynak düzenleyicileri ve [Sınıf Sihirbazı](mfc-class-wizard.md) içinde iletileri işleyici işlevlerinize eşlemek için kullanılır. Tüm standart komutların **bir ID_** öneki vardır. Örneğin, menü düzenleyicisini kullandığınızda, normalde Dosya Aç menü öğesini standart ID_FILE_OPEN komut kimliğine bağlarsınız.

Çoğu standart komut için uygulama kodunun komut kimliğine başvurması gerekmez, çünkü çerçevenin kendisi komutları birincil`CWinThread`çerçeve `CWinApp` `CView`sınıflarında (, , , `CDocument`, vb.) ileti eşlemleri aracılığıyla işler.

Standart komut iD'lerine ek olarak, **AFX_ID**öneki olan bir dizi başka standart dis tanımlanır. Bu d'ler standart pencere itlemi (önek **AFX_IDW_),** dize ii (önek **AFX_IDS_)** ve diğer birkaç türü içerir.

**AFX_ID** önekiile başlayan işlevler programcılar tarafından nadiren kullanılır, ancak **AFX_ID**s'ye de atıfta bulunan çerçeve işlevlerini geçersiz kılarak bu işlevlere başvurmanız gerekebilir.

Kimlikler bu başvuruda tek tek belgelenmez. Teknik Notlar [20,](../../mfc/tn020-id-naming-and-numbering-conventions.md) [21](../../mfc/tn021-command-and-message-routing.md)ve [22](../../mfc/tn022-standard-commands-implementation.md)onlar hakkında daha fazla bilgi bulabilirsiniz.

> [!NOTE]
> Afxres.h üstbilgi dosyası dolaylı olarak Afxwin.h'ye dahildir. Uygulamanızın kaynak komut dosyası (.rc) dosyasına aşağıdaki ifadeyi açıkça eklemeniz gerekir:

[!code-cpp[NVC_MFC_Utilities#47](../../mfc/codesnippet/cpp/standard-command-and-window-ids_1.h)]

## <a name="see-also"></a>Ayrıca bkz.

[Makrolar ve Küreseller](../../mfc/reference/mfc-macros-and-globals.md)
