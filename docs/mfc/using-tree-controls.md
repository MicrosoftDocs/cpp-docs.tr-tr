---
description: 'Hakkında daha fazla bilgi edinin: ağaç denetimlerini kullanma'
title: Ağaç Denetimlerini Kullanma
ms.date: 11/04/2016
helpviewer_keywords:
- CTreeCtrl class [MFC], using
- tree controls [MFC], about tree controls
ms.assetid: 4e92941a-e477-4fb1-b1ce-4abeafbef1c1
ms.openlocfilehash: 7b8a10acc3ee256f4b26c9988c4de7df900e1535
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97143201"
---
# <a name="using-tree-controls"></a>Ağaç Denetimlerini Kullanma

Bir ağaç denetiminin ([Ctreeci](../mfc/reference/ctreectrl-class.md)) tipik kullanımı aşağıdaki kalıbı izler:

- Denetim oluşturulur. Denetim bir iletişim kutusu şablonunda belirtilmişse veya kullanıyorsanız `CTreeView` , iletişim kutusu veya görünüm oluşturulduğunda, oluşturma otomatik olur. Ağaç denetimini başka bir pencerenin alt penceresi olarak oluşturmak istiyorsanız üye [Oluştur](../mfc/reference/ctreectrl-class.md#create) işlevini kullanın.

- Ağaç denetiminizin görüntü kullanmasını istiyorsanız [SetImageList](../mfc/reference/ctreectrl-class.md#setimagelist)' i çağırarak bir görüntü listesi ayarlayın. Ayrıca, [Setgirintiyi](../mfc/reference/ctreectrl-class.md#setindent)çağırarak Girintiyi değiştirebilirsiniz. Bunu yapmak için iyi bir zaman [OnInitDialog](../mfc/reference/cdialog-class.md#oninitdialog) (iletişim kutularındaki denetimler için) veya [OnInitialUpdate](../mfc/reference/cview-class.md#oninitialupdate) (görünümler için).

- `CTreeCtrl`Her veri öğesi için bir kez [InsertItem](../mfc/reference/ctreectrl-class.md#insertitem) işlevini çağırarak denetime veri koyun. `InsertItem` alt öğeler eklenirken olduğu gibi, daha sonra başvurmak için kullanabileceğiniz öğeye yönelik bir tanıtıcı döndürür. Verilerin başlatılması için uygun bir zaman `OnInitDialog` (iletişim kutularındaki denetimler için) veya `OnInitialUpdate` (görünümler için).

- Kullanıcı denetimle etkileşime geçtiğinde, çeşitli bildirim iletileri gönderilir. Denetim pencerenizin ileti eşlemesine bir ON_NOTIFY_REFLECT makrosu ekleyerek veya üst pencerenizin ileti eşlemesine bir ON_NOTIFY makrosu ekleyerek, işlemek istediğiniz her bir iletiyi işlemek için bir işlev belirtebilirsiniz. Olası bildirimlerin listesi için bu konunun ilerleyen kısımlarında bulunan [Ağaç denetimi bildirim iletileri](../mfc/tree-control-notification-messages.md) bölümüne bakın.

- Denetimin değerlerini ayarlamak için çeşitli set member işlevlerini çağırın. Yapabileceğiniz değişiklikler, girintileme ayarlamayı ve metin, resim veya bir öğeyle ilişkili verilerin değiştirilmesini kapsar.

- Denetimin içeriğini incelemek için çeşitli Get işlevlerini kullanın. Ayrıca, belirli bir öğenin üst, alt ve eşdüzey öğelerine yönelik tutamaçları almanızı sağlayan işlevlerle ağaç denetimi içeriğini de çapraz taşıyabilirsiniz. Hatta belirli bir düğümün alt öğelerini sıralayabilirsiniz.

- Denetim ile işiniz bittiğinde, düzgün şekilde yok edildiğinizden emin olun. Ağaç denetimi bir iletişim kutusunda ise veya bir görünümse, bu ve `CTreeCtrl` nesnesi otomatik olarak yok edilir. Aksi takdirde, hem denetimin hem de `CTreeCtrl` nesnenin düzgün şekilde yok edildiğini güvence altına almanız gerekir.

## <a name="see-also"></a>Ayrıca bkz.

[CTreeCtrl Kullanma](../mfc/using-ctreectrl.md)<br/>
[Denetimler](../mfc/controls-mfc.md)
