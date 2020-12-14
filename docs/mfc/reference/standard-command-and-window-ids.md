---
description: 'Daha fazla bilgi edinin: standart komut ve pencere kimlikleri'
title: Standart Komut ve Pencere Kimlikleri
ms.date: 11/04/2016
helpviewer_keywords:
- standard command and Window IDs
ms.assetid: 0424805c-fff8-4531-8f0c-15cfb13aa612
ms.openlocfilehash: 9f5a6b59d9451d749a48443bddf3560d2702bfe5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97218907"
---
# <a name="standard-command-and-window-ids"></a>Standart Komut ve Pencere Kimlikleri

Microsoft Foundation Class Kitaplığı, afxres. h içinde bir dizi standart komut ve pencere kimliği tanımlar. Bu kimlikler en yaygın olarak kaynak düzenleyicilerinde ve [sınıf Sihirbazı](mfc-class-wizard.md) 'nda, iletileri işleyici işlevleriniz ile eşlemek için kullanılır. Tüm standart komutların **ID_** öneki vardır. Örneğin, menü düzenleyicisini kullandığınızda, normalde dosya açma menü öğesini standart ID_FILE_OPEN komut KIMLIĞINE bağlarsınız.

Çoğu standart komut için, Framework 'ün kendisini birincil çerçeve sınıflarında (,,, vb `CWinThread` `CWinApp` `CView` .) ileti eşlemeleri aracılığıyla işletiğinden, uygulama kodunun komut kimliğine başvurması gerekmez `CDocument` .

Standart komut kimliklerine ek olarak, **AFX_ID** ön ekine sahip olan bir dizi diğer standart kimlik tanımlanmıştır. Bu kimlikler standart pencere kimliklerini (önek      **AFX_IDW_**), dize kimliklerini (ön ek **AFX_IDS_**) ve diğer birçok türü içerir.

**AFX_ID** önekiyle başlayan kimlikler, programcılar tarafından nadiren kullanılır, ancak **AFX_ID** s 'ye de başvuran çerçeve işlevlerini geçersiz kılarken bu kimliklere başvurmanız gerekebilir.

Kimlikler bu başvuruda tek tek açıklanmamıştır. Bu bilgiler hakkında daha fazla bilgi edinmek için bkz. Teknik notlarda [20](../../mfc/tn020-id-naming-and-numbering-conventions.md), [21](../../mfc/tn021-command-and-message-routing.md)ve [22](../../mfc/tn022-standard-commands-implementation.md).

> [!NOTE]
> Afxres. h başlık dosyası, Afxwin. h 'ye dolaylı olarak dahildir. Uygulamanızın kaynak komut dosyası (. RC) dosyasına aşağıdaki ifadeyi açıkça eklemeniz gerekir:

[!code-cpp[NVC_MFC_Utilities#47](../../mfc/codesnippet/cpp/standard-command-and-window-ids_1.h)]

## <a name="see-also"></a>Ayrıca bkz.

[Makrolar ve genel öğeler](../../mfc/reference/mfc-macros-and-globals.md)
