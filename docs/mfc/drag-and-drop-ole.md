---
title: Sürükleme ve Bırakma (OLE)
ms.date: 11/04/2016
helpviewer_keywords:
- OLE server applications [MFC], drag and drop
- drag and drop [MFC]
- OLE applications [MFC], drag and drop
- File Manager drag and drop support [MFC]
- drag and drop [MFC], about OLE drag and drop
- OLE drag and drop [MFC]
ms.assetid: a4595350-ca06-4400-88a1-f0175c76b77b
ms.openlocfilehash: 98bd58745e56a62bf5700e9b5fe4963a7b584953
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62405930"
---
# <a name="drag-and-drop-ole"></a>Sürükleme ve Bırakma (OLE)

OLE sürükle/bırak özelliğini veri kopyalama ve yapıştırma için öncelikle bir kısayol bulunur. Veya veri kopyalamak için Pano'yu kullandığınızda, bir dizi adımı gereklidir. Veri seçip tıklayın **Kes** veya **kopyalama** gelen **Düzenle** menüsünde, hedef dosya, pencere veya uygulama taşıma istenen konumu ve tıklatın imleci yerleştirin **Yapıştır** gelen **Düzenle** menüsü.

OLE sürükle ve bırak özellikle dosya adlarını uygulamaları geçirmek için tasarlanmıştır ve dosya adları yalnızca işleyebilir Dosya Yöneticisi sürükleme ve bırakma mekanizması farklıdır. OLE sürükle ve bırak daha çok genel. Panoda ayrıca yerleştirilebilir herhangi bir veri sürükleyip olanak tanır.

OLE sürükle ve bırak kullandığınızda, işlemden iki adımları kaldırabilirsiniz. Veri kaynağı penceresinden ("bırakma kaynağı") seçin, hedef ("bırakma hedefi") istenen konuma sürükleyin ve fare düğmesini serbest bırakarak bırakın. İşlem menüleri ihtiyacını ortadan kaldırır ve kopyala/yapıştır sırası hızlıdır. Tek gereksinim bırakma kaynağı ve bırakma hedefi açık ve en azından kısmen görünür ekranında olması gerekliliğidir.

OLE sürükle ve bırak kullanarak, verileri bir konumdan diğerine uygulamalar arasında veya farklı belgelerini bir belge içindeki aktarılabilir. Bir kapsayıcı veya bir sunucu uygulaması uygulanabilir ve herhangi bir uygulama bir bırakma kaynağı, bir bırakma hedefi veya her ikisi de olabilir. Bir uygulamanın uygulanan hem bırakma kaynağı hem de bırakma hedefi destek varsa, sürükle ve bırak etkin alt pencereler arasında veya bir pencere içinde. Bu özellik, uygulamanızı kullanmak çok daha kolay hale getirebilirsiniz.

OLE sürükle ve bırak özelliklerini kullanmak istiyorsanız, bkz [sürükle ve bırak: Özelleştirme](../mfc/drag-and-drop-customizing.md). OLE dışı uygulamalar kaynakları bırakın yapmak için bu makalede açıklanan teknikleri kullanabilirsiniz. Makaleyi [sürükle ve bırak: Bir bırakma hedefi uygulama](../mfc/drag-and-drop-implementing-a-drop-target.md) OLE hem OLE olmayan uygulamaları için destek bırakma hedefi uygulama açıklar. Bu da MFC OLE örnekleri incelemek yararlı olacaktır [OCLIENT](../overview/visual-cpp-samples.md) ve [HIERSVR](../overview/visual-cpp-samples.md).

Değil okumadıysanız [veri nesneleri ve veri kaynakları (OLE)](../mfc/data-objects-and-data-sources-ole.md) makaleleri ailesi, bunu şimdi yapmak isteyebilirsiniz. Bu makaleler, veri aktarımı ve uygulamalarınızda nasıl temellerini açıklar.

Sürükleme ve bırakma hakkında daha fazla bilgi için bkz:

- [Sürükleme ve Bırakma: Bırakma Kaynağı Uygulama](../mfc/drag-and-drop-implementing-a-drop-source.md)

- [Sürükleme ve Bırakma: Bırakma Hedefi Uygulama](../mfc/drag-and-drop-implementing-a-drop-target.md)

- [Sürükleme ve Bırakma: Özelleştirme](../mfc/drag-and-drop-customizing.md)

## <a name="see-also"></a>Ayrıca bkz.

[OLE](../mfc/ole-in-mfc.md)<br/>
[Veri Nesneleri ve Veri Kaynakları (OLE)](../mfc/data-objects-and-data-sources-ole.md)
