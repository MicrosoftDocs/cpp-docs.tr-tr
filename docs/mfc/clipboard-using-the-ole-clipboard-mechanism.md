---
title: 'Pano: OLE panosu mekanizmasını kullanma'
ms.date: 11/04/2016
helpviewer_keywords:
- applications [OLE], Clipboard
- OLE Clipboard
- Clipboard [MFC], OLE formats
- OLE Clipboard, formats
- formats [MFC], Clipboard for OLE
ms.assetid: 229cc610-5bb1-435e-bd20-2c8b9964d1af
ms.openlocfilehash: 0f2c10f4a88b723d1ab9f4bb0ca903987359c9fd
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69508912"
---
# <a name="clipboard-using-the-ole-clipboard-mechanism"></a>Pano: OLE panosu mekanizmasını kullanma

OLE, verileri pano aracılığıyla aktarmaya yönelik standart biçimleri ve OLE 'ye özgü bazı biçimleri kullanır.

Bir uygulamadan veri kestiğinizde veya kopyaladığınızda, veriler daha sonra yapıştırma işlemlerinde kullanılmak üzere panoda depolanır. Bu veriler çeşitli biçimlerde. Kullanıcı panodan veri yapıştırmayı seçtiğinde, bu biçimlerden hangisini kullanacağınızı tercih edebilir. Kullanıcı özel olarak belirli bir biçim istediğinde Özel Yapıştır seçeneğini kullanarak en çok bilgiyi sağlayan biçimi seçmek için uygulamanın yazılması gerekir. Devam etmeden önce [veri nesneleri ve veri kaynakları (OLE)](../mfc/data-objects-and-data-sources-ole.md) konularını okumak isteyebilirsiniz. Bunlar, verilerin nasıl çalıştığı ve uygulamalarınızda nasıl uygulanacağı hakkında temel bilgileri açıklamaktadır.

Windows, pano aracılığıyla veri aktarımı için kullanılabilen bir dizi standart biçimi tanımlar. Bunlar arasında meta dosyaları, metin, bit eşlemler ve diğerleri bulunur. OLE, bir dizi OLE 'e özgü biçimi de tanımlar. Bu standart biçimlerin verilenden daha fazla ayrıntı gerektiren uygulamalar için kendi özel Pano biçimlerini kaydetmek iyi bir fikirdir. Bunu yapmak için [RegisterClipboardFormat](/windows/win32/api/winuser/nf-winuser-registerclipboardformatw) Win32 API işlevini kullanın.

Örneğin, Microsoft Excel elektronik tablolar için özel bir biçim kaydeder. Bu biçim, örneğin bir bit eşlem gibi çok daha fazla bilgi taşır. Bu veriler, elektronik tablo biçimini destekleyen bir uygulamaya yapıştırıldığında, elektronik tablodaki tüm formüller ve değerler korunur ve gerekirse güncelleştirilecektir. Ayrıca, Microsoft Excel, bir OLE öğesi olarak yapıştırılabilmesi için panodaki verileri biçimlere de yerleştirir. Herhangi bir OLE belge kapsayıcısı, bu bilgileri katıştırılmış öğe olarak yapıştırabilir. Bu ekli öğe, Microsoft Excel kullanılarak değiştirilebilir. Panoda Ayrıca, elektronik tabloda seçilen aralığın görüntüsünün basit bir bit eşlemi de bulunur. Bu Ayrıca, OLE belge kapsayıcılarına veya Paint gibi bit eşlem düzenleyicilerine de yapıştırılabilir. Ancak bir bit eşlem söz konusu olduğunda, verileri bir elektronik tablo olarak kullanmanın bir yolu yoktur.

Panodan en fazla bilgi miktarını almak için, uygulamalar panodan verileri yapıştırmadan önce bu özel biçimleri denetlemelidir.

Örneğin, Kes komutunu etkinleştirmek için, aşağıdakine benzer bir işleyici yazabilirsiniz:

[!code-cpp[NVC_MFCListView#3](../atl/reference/codesnippet/cpp/clipboard-using-the-ole-clipboard-mechanism_1.cpp)]

## <a name="what-do-you-want-to-know-more-about"></a>Hakkında daha fazla bilgi edinmek istiyorsunuz

- [Verileri kopyalama ve yapıştırma](../mfc/clipboard-copying-and-pasting-data.md)

- [Diğer biçimleri ekleme](../mfc/clipboard-adding-other-formats.md)

- [Windows panosunu kullanma](../mfc/clipboard-using-the-windows-clipboard.md)

- [NESNE](../mfc/ole-background.md)

- [OLE veri nesneleri ve veri kaynakları ve Tekdüzen veri aktarımı](../mfc/data-objects-and-data-sources-ole.md)

## <a name="see-also"></a>Ayrıca bkz.

[Pano](../mfc/clipboard.md)
