---
title: 'Pano: OLE Pano Mekanizmasını Kullanma'
ms.date: 11/04/2016
helpviewer_keywords:
- applications [OLE], Clipboard
- OLE Clipboard
- Clipboard [MFC], OLE formats
- OLE Clipboard, formats
- formats [MFC], Clipboard for OLE
ms.assetid: 229cc610-5bb1-435e-bd20-2c8b9964d1af
ms.openlocfilehash: 3dadd2ae6774c684fe751e02fb3a80570accd30a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50661454"
---
# <a name="clipboard-using-the-ole-clipboard-mechanism"></a>Pano: OLE Pano Mekanizmasını Kullanma

OLE Pano aracılığıyla verileri aktarmak için standard biçimleri ve bazı özel OLE biçimleri kullanır.

Keser veya bir uygulamadan veri kopyalama, yapıştırma işlemlerinde daha sonra kullanılmak üzere Pano veri depolanır. Çeşitli biçimlerde verilerdir. Pano verileri yapıştırmak kullanıcı seçtiğinde uygulama hangilerini kullanmak için aşağıdaki biçimlerden birini seçebilirsiniz. Özellikle belirli bir bir biçimde için Özel Yapıştır kullanarak kullanıcıdan sürece çoğu bilgi sağlayan biçimi seçmek için uygulamayı yeniden yazılması gerekir. Devam etmeden önce okumak isteyebilirsiniz [veri nesneleri ve veri kaynakları (OLE)](../mfc/data-objects-and-data-sources-ole.md) konuları. Bunlar nasıl iş verileri aktarır ve bunları uygulamalarınızda uygulama nasıl temellerini açıklar.

Windows, bir dizi Pano aracılığıyla verileri aktarmak için kullanılabilecek standart biçimlerini tanımlar. Bunlar, meta dosyaları, metin, bit eşlemler ve diğerleri içerir. OLE de OLE özel biçimler sayısını tanımlar. Bu standart biçimler tarafından verilen daha ayrıntılı gerek duyan uygulamalar için kendi özel Pano biçimlerini kaydetmek için bir fikirdir. Win32 API işlevi kullanmanız [RegisterClipboardFormat](/windows/desktop/api/winuser/nf-winuser-registerclipboardformata) Bunu yapmak için.

Örneğin, Microsoft Excel elektronik tablolar için özel bir biçim kaydeder. Bu biçim taşıyan çok daha fazla bilgi, örneğin, bir bit eşlem yok. Bu veri elektronik tablo biçiminde destekleyen bir uygulama yapıştırıldığında, formüller ve elektronik tablodaki değerleri korunur ve gerekirse güncelleştirilebilir. OLE öğesini yapıştırılabilmesi için Microsoft Excel veri biçimleri Pano'ya ayrıca koyar. Tüm OLE belge kapsayıcısı, bu bilgileri gömülü bir öğe olarak yapıştırabilirsiniz. Microsoft Excel kullanılarak bu gömülü bir öğe değiştirilebilir. Pano, bir basit bit eşlem elektronik tablosundaki Seçili aralık görüntüsü de içerir. Bu da OLE belge kapsayıcıları veya Boya gibi bit eşlem düzenleyicileri yapıştırılabilir. Bir bit eşlem söz konusu olduğunda, ancak bir elektronik tablo olarak verileri işlemek için hiçbir yolu yoktur.

Panodan en çok bilgi almak için uygulamalar Pano verilerini yapıştırma önce bu özel biçimler için denetlemelisiniz.

Örneğin, Cut komutu etkinleştirmek için bir işleyici aşağıdakine benzer bir şey yazabiliriz:

[!code-cpp[NVC_MFCListView#3](../atl/reference/codesnippet/cpp/clipboard-using-the-ole-clipboard-mechanism_1.cpp)]

## <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz

- [Veri kopyalama ve yapıştırma](../mfc/clipboard-copying-and-pasting-data.md)

- [Diğer biçimleri ekleme](../mfc/clipboard-adding-other-formats.md)

- [Windows panosunu kullanma](../mfc/clipboard-using-the-windows-clipboard.md)

- [OLE](../mfc/ole-background.md)

- [OLE veri nesneleri ve veri kaynaklarını ve Tekdüzen veri aktarımı](../mfc/data-objects-and-data-sources-ole.md)

## <a name="see-also"></a>Ayrıca Bkz.

[Pano](../mfc/clipboard.md)

