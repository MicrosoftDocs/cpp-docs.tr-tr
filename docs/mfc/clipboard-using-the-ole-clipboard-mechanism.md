---
description: 'Şu konuda daha fazla bilgi edinin: Pano: OLE Pano mekanizmasını kullanma'
title: 'Pano: OLE Pano Mekanizmasını Kullanma'
ms.date: 11/04/2016
helpviewer_keywords:
- applications [OLE], Clipboard
- OLE Clipboard
- Clipboard [MFC], OLE formats
- OLE Clipboard, formats
- formats [MFC], Clipboard for OLE
ms.assetid: 229cc610-5bb1-435e-bd20-2c8b9964d1af
ms.openlocfilehash: f7005bd3e99ebb658b6aa38952a6689d4a9ba30c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97338432"
---
# <a name="clipboard-using-the-ole-clipboard-mechanism"></a>Pano: OLE Pano Mekanizmasını Kullanma

OLE, verileri pano aracılığıyla aktarmaya yönelik standart biçimleri ve OLE 'ye özgü bazı biçimleri kullanır.

Bir uygulamadan veri kestiğinizde veya kopyaladığınızda, veriler daha sonra yapıştırma işlemlerinde kullanılmak üzere panoda depolanır. Bu veriler çeşitli biçimlerde. Kullanıcı panodan veri yapıştırmayı seçtiğinde, bu biçimlerden hangisini kullanacağınızı tercih edebilir. Kullanıcı özel olarak belirli bir biçim istediğinde Özel Yapıştır seçeneğini kullanarak en çok bilgiyi sağlayan biçimi seçmek için uygulamanın yazılması gerekir. Devam etmeden önce [veri nesneleri ve veri kaynakları (OLE)](data-objects-and-data-sources-ole.md) konularını okumak isteyebilirsiniz. Bunlar, verilerin nasıl çalıştığı ve uygulamalarınızda nasıl uygulanacağı hakkında temel bilgileri açıklamaktadır.

Windows, pano aracılığıyla veri aktarımı için kullanılabilen bir dizi standart biçimi tanımlar. Bunlar arasında meta dosyaları, metin, bit eşlemler ve diğerleri bulunur. OLE, bir dizi OLE 'e özgü biçimi de tanımlar. Bu standart biçimlerin verilenden daha fazla ayrıntı gerektiren uygulamalar için kendi özel Pano biçimlerini kaydetmek iyi bir fikirdir. Bunu yapmak için [RegisterClipboardFormat](/windows/win32/api/winuser/nf-winuser-registerclipboardformatw) Win32 API işlevini kullanın.

Örneğin, Microsoft Excel elektronik tablolar için özel bir biçim kaydeder. Bu biçim, örneğin bir bit eşlem gibi çok daha fazla bilgi taşır. Bu veriler, elektronik tablo biçimini destekleyen bir uygulamaya yapıştırıldığında, elektronik tablodaki tüm formüller ve değerler korunur ve gerekirse güncelleştirilecektir. Ayrıca, Microsoft Excel, bir OLE öğesi olarak yapıştırılabilmesi için panodaki verileri biçimlere de yerleştirir. Herhangi bir OLE belge kapsayıcısı, bu bilgileri katıştırılmış öğe olarak yapıştırabilir. Bu ekli öğe, Microsoft Excel kullanılarak değiştirilebilir. Panoda Ayrıca, elektronik tabloda seçilen aralığın görüntüsünün basit bir bit eşlemi de bulunur. Bu Ayrıca, OLE belge kapsayıcılarına veya Paint gibi bit eşlem düzenleyicilerine de yapıştırılabilir. Ancak bir bit eşlem söz konusu olduğunda, verileri bir elektronik tablo olarak kullanmanın bir yolu yoktur.

Panodan en fazla bilgi miktarını almak için, uygulamalar panodan verileri yapıştırmadan önce bu özel biçimleri denetlemelidir.

Örneğin, Kes komutunu etkinleştirmek için, aşağıdakine benzer bir işleyici yazabilirsiniz:

[!code-cpp[NVC_MFCListView#3](../atl/reference/codesnippet/cpp/clipboard-using-the-ole-clipboard-mechanism_1.cpp)]

## <a name="what-do-you-want-to-know-more-about"></a>Hakkında daha fazla bilgi edinmek istiyorsunuz

- [Verileri kopyalama ve yapıştırma](clipboard-copying-and-pasting-data.md)

- [Diğer biçimleri ekleme](clipboard-adding-other-formats.md)

- [Windows panosunu kullanma](clipboard-using-the-windows-clipboard.md)

- [OLE](ole-background.md)

- [OLE veri nesneleri ve veri kaynakları ve Tekdüzen veri aktarımı](data-objects-and-data-sources-ole.md)

## <a name="see-also"></a>Ayrıca bkz.

[Pano](clipboard.md)
