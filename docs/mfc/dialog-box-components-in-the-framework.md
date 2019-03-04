---
title: Framework'te İletişim Kutusu Bileşenleri
ms.date: 11/04/2016
helpviewer_keywords:
- MFC dialog boxes [MFC], creating
- dialog classes [MFC], dialog box components
- MFC dialog boxes [MFC], about MFC dialog boxes
- dialog templates [MFC], MFC framework
- MFC dialog boxes [MFC], dialog resource
ms.assetid: 592db160-0a8a-49be-ac72-ead278aca53f
ms.openlocfilehash: 88027df7433267925e91db2d368b744cee8a9e75
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57262746"
---
# <a name="dialog-box-components-in-the-framework"></a>Framework'te İletişim Kutusu Bileşenleri

MFC çerçevesi içinde bir iletişim kutusu iki bileşenden oluşur:

- İletişim kutusunun denetimleri ve bunların yerleştirme belirten bir iletişim şablonunu kaynağıdır.

   İletişim kaynağını Windows iletişim kutusu penceresini oluşturur ve görüntüler, bir iletişim şablonunu depolar. Şablonu, boyutunu, konumu, stil ve türleri ve iletişim kutusunun denetimleri konumlarını dahil olmak üzere, iletişim kutusunun özelliklerini belirtir. Genellikle, bir kaynak olarak depolanan bir iletişim şablonunu kullanır, ancak ayrıca bellekte kendi şablonunuzu oluşturabilirsiniz.

- Bir iletişim kutusu sınıfı türetilen [CDialog](../mfc/reference/cdialog-class.md), iletişim kutusu yönetmek için bir programlama arabirimi sağlar.

   Bir iletişim kutusu, bir pencere ve bir Windows penceresi görünür olduğunda eklenir. İletişim kutusu penceresi oluşturulurken iletişim şablon kaynağı alt iletişim kutusu için pencere denetimleri oluşturmak için şablon olarak kullanılır.

## <a name="see-also"></a>Ayrıca bkz.

[İletişim Kutuları](../mfc/dialog-boxes.md)<br/>
[Bir İletişim Kutusunun Yaşam Döngüsü](../mfc/life-cycle-of-a-dialog-box.md)
