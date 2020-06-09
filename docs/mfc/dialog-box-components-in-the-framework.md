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
ms.openlocfilehash: b3290107337f60854e6abbd2f744aaa38af0b741
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84616919"
---
# <a name="dialog-box-components-in-the-framework"></a>Framework'te İletişim Kutusu Bileşenleri

MFC çerçevesinde, bir iletişim kutusunun iki bileşeni vardır:

- İletişim kutusunun denetimlerini ve onların yerleşimini belirten bir iletişim kutusu-şablon kaynağı.

   İletişim kaynağı, Windows 'un iletişim kutusu penceresini oluşturduğu bir iletişim kutusu şablonunu depolar ve görüntüler. Şablon, iletişim kutusunun kendi boyut, konum, stili ve iletişim kutusu denetimlerinin türleri ve konumları dahil olmak üzere iletişim kutusu özelliklerini belirtir. Genellikle kaynak olarak depolanan bir iletişim kutusu şablonunu kullanacaksınız, ancak bellekte kendi şablonunuzu da oluşturabilirsiniz.

- İletişim kutusunun yönetilmesine yönelik bir programlama arabirimi sağlamak için [CDialog](reference/cdialog-class.md)'dan türetilen bir iletişim kutusu sınıfı.

   Bir iletişim kutusu pencere olur ve görünür olduğunda bir Windows penceresine eklenecektir. İletişim kutusu penceresi oluşturulduğunda, iletişim kutusu için alt pencere denetimleri oluşturmak için bir şablon olarak iletişim kutusu-şablon kaynağı kullanılır.

## <a name="see-also"></a>Ayrıca bkz.

[İletişim Kutuları](dialog-boxes.md)<br/>
[MFC’de İletişim Kutularıyla çalışma](life-cycle-of-a-dialog-box.md)
