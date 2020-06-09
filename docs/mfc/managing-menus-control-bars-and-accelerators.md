---
title: Menüleri, Denetim Çubuklarını ve Hızlandırıcıları Yönetme
ms.date: 11/04/2016
helpviewer_keywords:
- MDI [MFC], frame windows
- control bars [MFC], updating in frame windows
- menus [MFC], updating as context changes
- user interface objects [MFC], updating
- accelerator tables [MFC]
- sharing menus [MFC]
- updating user-interface objects [MFC]
- frame windows [MFC], updating
- status bars [MFC], updating
ms.assetid: 97ca1997-06df-4373-b023-4f7ecd81047b
ms.openlocfilehash: 9945dc68ffd46bbf5e114a79467299e4b67e3659
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84621322"
---
# <a name="managing-menus-control-bars-and-accelerators"></a>Menüleri, Denetim Çubuklarını ve Hızlandırıcıları Yönetme

Çerçeve penceresi, menüler, araç çubuğu düğmeleri, durum çubuğu ve Hızlandırıcılar dahil olmak üzere Kullanıcı arabirimi nesnelerinin güncelleştirilmesini yönetir. Ayrıca MDI uygulamalarında menü çubuğunun paylaşımını da yönetir.

## <a name="managing-menus"></a>Menüleri yönetme

Çerçeve penceresi, Kullanıcı arabirimi [nesnelerini güncelleştirme](how-to-update-user-interface-objects.md)bölümünde açıklanan ON_UPDATE_COMMAND_UI mekanizmasını kullanarak Kullanıcı arabirimi öğelerini güncelleştirmede yer alır. Araç çubuklarındaki ve diğer denetim çubuklarındaki düğmeler, boşta döngüsü sırasında güncellenir. Menü çubuğundaki açılan menülerde menü öğeleri, menü kapatılmadan hemen önce güncelleştirilir.

MDI uygulamaları için, MDI çerçevesi penceresi menü çubuğunu ve resim yazısını yönetir. Bir MDI çerçevesi penceresi, etkin bir MDI alt pencereleri olmadığında menü çubuğu olarak kullanılan bir varsayılan menünün sahibidir. Etkin alt öğeler olduğunda, MDI çerçeve penceresinin menü çubuğu, etkin MDI alt penceresi için olan menü tarafından alınır. Bir MDI uygulaması, grafik ve çalışma sayfası belgeleri gibi birden çok belge türünü destekliyorsa, her tür menü çubuğuna kendi menülerini koyar ve ana çerçeve penceresinin başlığını değiştirir.

[Cmdiframewnd](reference/cmdiframewnd-class.md) , MDI uygulamaları Için görüntülenen pencere menüsünde standart komutlar için varsayılan uygulamalar sağlar. Özellikle yeni pencere komutu (ID_WINDOW_NEW), yeni bir çerçeve penceresi oluşturmak ve geçerli belgede görüntülemek için uygulanır. Bu uygulamaları yalnızca gelişmiş özelleştirmeye ihtiyacınız varsa geçersiz kılmanız gerekir.

Aynı belge türüne sahip birden çok MDI alt penceresi, menü kaynakları paylaşır. Aynı belge şablonu tarafından çeşitli MDI alt pencereleri oluşturulduysa, hepsi Windows 'daki sistem kaynaklarına kaydederek aynı menü kaynağını kullanabilirler.

## <a name="managing-the-status-bar"></a>Durum çubuğunu yönetme

Çerçeve penceresi ayrıca, istemci alanı içinde durum çubuğunu konumlandırır ve durum çubuğunun göstergelerini yönetir. Çerçeve penceresi, durum çubuğundaki ileti alanını temizler ve güncelleştirir ve Kullanıcı, [durum çubuğunda komut bilgilerini görüntüleme](how-to-display-command-information-in-the-status-bar.md)bölümünde açıklandığı gibi menü öğeleri veya araç çubuğu düğmeleri seçtiğinde istem dizelerini görüntüler.

## <a name="managing-accelerators"></a>Hızlandırıcıları yönetme

Her çerçeve penceresinde otomatik olarak klavye Hızlandırıcısı çevirisi sağlayan isteğe bağlı bir Hızlandırıcı tablosu korunur. Bu mekanizma, menü komutlarını çağıran Hızlandırıcı tuşlarını (kısayol tuşları da denir) tanımlamanızı kolaylaştırır.

## <a name="see-also"></a>Ayrıca bkz.

[Çerçeve pencerelerini kullanma](using-frame-windows.md)
