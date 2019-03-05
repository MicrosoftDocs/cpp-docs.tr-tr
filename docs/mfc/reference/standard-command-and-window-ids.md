---
title: Standart Komut ve Pencere Kimlikleri
ms.date: 11/04/2016
f1_keywords:
- vc.mfc.macros
helpviewer_keywords:
- standard command and Window IDs
ms.assetid: 0424805c-fff8-4531-8f0c-15cfb13aa612
ms.openlocfilehash: e5f6955407f565d5cc06ef57e9bd273f6c0f7712
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57267257"
---
# <a name="standard-command-and-window-ids"></a>Standart Komut ve Pencere Kimlikleri

Microsoft Foundation Class Kitaplığı Afxres.h içinde bir dizi standart komut ve pencere kimlikleri tanımlar. Bu kimlikleri, işleyici işlevleri için ileti eşlemesi için kaynak düzenleyicileri ve Özellikler penceresi içinde en yaygın olarak kullanılır. Tüm standart komutlar sahip bir **ID_** önek. Menü Düzenleyicisi'ni kullandığınızda, örneğin, normalde Dosya Aç menü öğesi standart ıd_fıle_open komutu kimliğine bağlama

Komutları birincil framework sınıflarına ileti eşlemelerinin framework işlemesi nedeniyle çoğu standart komutlar için uygulama kodu komutu Kimliğine bakın gerekmez (`CWinThread`, `CWinApp`, `CView`, `CDocument`, ve vb.).

Standart komut kimlikleri ek olarak, bir ön eki olan diğer standart kimlikleri sayısı tanımlanır, **AFX_ID**. Standart pencere kimlikleri bu kimliklerinin içerir (ön eki **AFX_IDW_**), kimlikleri dize (ön eki **AFX_IDS_**) ve birçok diğer türüne.

Şununla kimlikleri **AFX_ID** önek nadiren programcılar tarafından kullanılır, ancak bu kimlikler için de bkz framework işlevleri geçersiz kılarken başvurmanız gerekebilir **AFX_ID**s.

Bu başvuruda kimlikleri ayrı ayrı belgelenmemiştir. Teknik notlar bunlar üzerinde daha fazla bilgi bulabilirsiniz [20](../../mfc/tn020-id-naming-and-numbering-conventions.md), [21](../../mfc/tn021-command-and-message-routing.md), ve [22](../../mfc/tn022-standard-commands-implementation.md).

> [!NOTE]
>  Üst bilgi dosyası Afxres.h içinde Afxwin.h dolaylı olarak dahil edilir. Aşağıdaki deyim, uygulamanızın kaynak betiği (.rc) dosyasında açıkça eklemeniz gerekir:

[!code-cpp[NVC_MFC_Utilities#47](../../mfc/codesnippet/cpp/standard-command-and-window-ids_1.h)]

## <a name="see-also"></a>Ayrıca bkz.

[Makroları ve genel öğeleri](../../mfc/reference/mfc-macros-and-globals.md)
