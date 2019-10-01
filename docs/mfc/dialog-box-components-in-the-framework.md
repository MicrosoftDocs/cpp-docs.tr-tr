---
title: Çerçevede iletişim kutusu bileşenleri
ms.date: 11/04/2016
helpviewer_keywords:
- MFC dialog boxes [MFC], creating
- dialog classes [MFC], dialog box components
- MFC dialog boxes [MFC], about MFC dialog boxes
- dialog templates [MFC], MFC framework
- MFC dialog boxes [MFC], dialog resource
ms.assetid: 592db160-0a8a-49be-ac72-ead278aca53f
ms.openlocfilehash: 15d01924be811a9c9ec8ea333870f444bf9aa61a
ms.sourcegitcommit: 1e6386be9084f70def7b3b8b4bab319a117102b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/30/2019
ms.locfileid: "71685837"
---
# <a name="dialog-box-components-in-the-framework"></a>Çerçevede iletişim kutusu bileşenleri

MFC çerçevesinde, bir iletişim kutusunun iki bileşeni vardır:

- İletişim kutusunun denetimlerini ve onların yerleşimini belirten bir iletişim kutusu-şablon kaynağı.

   İletişim kaynağı, Windows 'un iletişim kutusu penceresini oluşturduğu bir iletişim kutusu şablonunu depolar ve görüntüler. Şablon, iletişim kutusunun kendi boyut, konum, stili ve iletişim kutusu denetimlerinin türleri ve konumları dahil olmak üzere iletişim kutusu özelliklerini belirtir. Genellikle kaynak olarak depolanan bir iletişim kutusu şablonunu kullanacaksınız, ancak bellekte kendi şablonunuzu da oluşturabilirsiniz.

- İletişim kutusunun yönetilmesine yönelik bir programlama arabirimi sağlamak için [CDialog](../mfc/reference/cdialog-class.md)'dan türetilen bir iletişim kutusu sınıfı.

   Bir iletişim kutusu pencere olur ve görünür olduğunda bir Windows penceresine eklenecektir. İletişim kutusu penceresi oluşturulduğunda, iletişim kutusu için alt pencere denetimleri oluşturmak için bir şablon olarak iletişim kutusu-şablon kaynağı kullanılır.

## <a name="see-also"></a>Ayrıca bkz.

[İletişim kutuları](../mfc/dialog-boxes.md)<br/>
[MFC 'de Iletişim kutularıyla çalışma](../mfc/life-cycle-of-a-dialog-box.md)
