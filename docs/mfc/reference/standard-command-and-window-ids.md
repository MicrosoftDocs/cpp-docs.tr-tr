---
title: Standart Komut ve Pencere Kimlikleri
ms.date: 11/04/2016
helpviewer_keywords:
- standard command and Window IDs
ms.assetid: 0424805c-fff8-4531-8f0c-15cfb13aa612
ms.openlocfilehash: 40783bc19e51afb0e9fe9e4a429df0239a8e7f09
ms.sourcegitcommit: 3caf5261b3ea80d9cf14038c116ba981d655cd13
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/11/2019
ms.locfileid: "70907712"
---
# <a name="standard-command-and-window-ids"></a>Standart Komut ve Pencere Kimlikleri

Microsoft Foundation Class Kitaplığı, afxres. h içinde bir dizi standart komut ve pencere kimliği tanımlar. Bu kimlikler en yaygın olarak kaynak düzenleyicilerinde ve [sınıf Sihirbazı](mfc-class-wizard.md) 'nda, iletileri işleyici işlevleriniz ile eşlemek için kullanılır. Tüm standart komutlarda bir **ID_** öneki vardır. Örneğin, menü düzenleyicisini kullandığınızda, normalde dosya açma menü öğesini standart ID_FILE_OPEN komut KIMLIĞINE bağlarsınız.

Çoğu standart komut için, çerçeve kendi birincil çerçeve`CWinThread`sınıflarında ( `CView`, `CWinApp` `CDocument`,, ve ' de ileti haritaları aracılığıyla komutları işlediği için uygulama kodunun komut kimliğine başvurması gerekmez). vb.).

Standart komut kimliklerine ek olarak, bir dizi diğer standart kimlik, **AFX_ID**öneki olan tanımlanmıştır. Bu kimlikler standart pencere kimliklerini (ön ek **AFX_IDW_** ), dize kimliklerini (önek **AFX_IDS_** ) ve diğer birçok türü içerir.

**AFX_ID** önekiyle başlayan kimlikler, programcılar tarafından nadiren kullanılır, ancak **AFX_ID**s öğesine de başvuran çerçeve işlevlerini geçersiz kılarken bu kimliklere başvurmanız gerekebilir.

Kimlikler bu başvuruda tek tek açıklanmamıştır. Bu bilgiler hakkında daha fazla bilgi edinmek için bkz. Teknik notlarda [20](../../mfc/tn020-id-naming-and-numbering-conventions.md), [21](../../mfc/tn021-command-and-message-routing.md)ve [22](../../mfc/tn022-standard-commands-implementation.md).

> [!NOTE]
>  Afxres. h başlık dosyası, Afxwin. h 'ye dolaylı olarak dahildir. Uygulamanızın kaynak komut dosyası (. RC) dosyasına aşağıdaki ifadeyi açıkça eklemeniz gerekir:

[!code-cpp[NVC_MFC_Utilities#47](../../mfc/codesnippet/cpp/standard-command-and-window-ids_1.h)]

## <a name="see-also"></a>Ayrıca bkz.

[Makrolar ve genel öğeler](../../mfc/reference/mfc-macros-and-globals.md)
