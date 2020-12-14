---
description: 'Daha fazla bilgi edinin: Framework içindeki Dialog-Box bileşenleri'
title: Framework'te İletişim Kutusu Bileşenleri
ms.date: 11/04/2016
helpviewer_keywords:
- MFC dialog boxes [MFC], creating
- dialog classes [MFC], dialog box components
- MFC dialog boxes [MFC], about MFC dialog boxes
- dialog templates [MFC], MFC framework
- MFC dialog boxes [MFC], dialog resource
ms.assetid: 592db160-0a8a-49be-ac72-ead278aca53f
ms.openlocfilehash: 406ffda122c6663d698f008a25164f8836221a2f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97261547"
---
# <a name="dialog-box-components-in-the-framework"></a>Framework'te İletişim Kutusu Bileşenleri

MFC çerçevesinde, bir iletişim kutusunun iki bileşeni vardır:

- İletişim kutusunun denetimlerini ve onların yerleşimini belirten bir iletişim kutusu-şablon kaynağı.

   İletişim kaynağı, Windows 'un iletişim kutusu penceresini oluşturduğu bir iletişim kutusu şablonunu depolar ve görüntüler. Şablon, iletişim kutusunun kendi boyut, konum, stili ve iletişim kutusu denetimlerinin türleri ve konumları dahil olmak üzere iletişim kutusu özelliklerini belirtir. Genellikle kaynak olarak depolanan bir iletişim kutusu şablonunu kullanacaksınız, ancak bellekte kendi şablonunuzu da oluşturabilirsiniz.

- İletişim kutusunun yönetilmesine yönelik bir programlama arabirimi sağlamak için [CDialog](reference/cdialog-class.md)'dan türetilen bir iletişim kutusu sınıfı.

   Bir iletişim kutusu pencere olur ve görünür olduğunda bir Windows penceresine eklenecektir. İletişim kutusu penceresi oluşturulduğunda, iletişim kutusu için alt pencere denetimleri oluşturmak için bir şablon olarak iletişim kutusu-şablon kaynağı kullanılır.

## <a name="see-also"></a>Ayrıca bkz.

[İletişim kutuları](dialog-boxes.md)<br/>
[MFC’de İletişim Kutularıyla çalışma](life-cycle-of-a-dialog-box.md)
