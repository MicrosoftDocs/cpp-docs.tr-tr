---
title: DHTML'den C++ kodu çağırma
ms.date: 11/04/2016
helpviewer_keywords:
- DHTML, calling C++ code from
ms.assetid: 37329acd-4c22-40ca-a85a-b7480748f75f
ms.openlocfilehash: fb63f8671770f57972a4c789d983bdf9658d5ecb
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62251742"
---
# <a name="calling-c-code-from-dhtml"></a>DHTML'den C++ kodu çağırma

DHTML denetimi Test kapsayıcısı veya Internet Explorer gibi bir kapsayıcıda barındırılabilir. Bkz: [Test kapsayıcısı ile test etme özellikleri ve olayları](../mfc/testing-properties-and-events-with-test-container.md) Test kapsayıcısı erişim hakkında daha fazla bilgi için.

Kapsayıcı denetim barındırma normal denetim arabirimleri kullanarak denetimi ile iletişim kurar. DHTML "C++ kodunuzu ve HTML kaynağınız ile iletişim kurmak için kullanıcı Arabirimi" ile biten gönderme arabirim kullanır. İçinde [ATL DHTML denetimini değiştirme](../atl/modifying-the-atl-dhtml-control.md), bu farklı arabirimleri tarafından çağrılan yöntemler ekleme alıştırma yapabilirsiniz.

DHTML'den C++ kodu çağırma örneği görmek için [DHTML denetimi oluşturma](../atl/creating-an-atl-dhtml-control.md) ATL denetimi Sihirbazı'nı kullanarak ve üstbilgi dosyası ve HTML dosyasındaki kodu inceleyin.

## <a name="declaring-webbrowser-methods-in-the-header-file"></a>WebBrowser yöntemleri üstbilgi dosyasında bildirme

DHTML arabiriminden C++ yöntemlerini çağırmak için yöntem denetiminizin UI arabirimine eklemeniz gerekir. Örneğin, C++ yöntemi ATL denetimi Sihirbazı tarafından oluşturulan üstbilgi dosyasını içeren `OnClick`, sihirbaz tarafından oluşturulan denetim UI arabiriminin üyesi olduğu.

İnceleme `OnClick` içinde denetim .h dosyası:

[!code-cpp[NVC_ATL_COM#4](../atl/codesnippet/cpp/calling-cpp-code-from-dhtml_1.h)]

İlk parametre *pdispBody*, gövde nesnenin gönderme arabirimi işaretçisidir. İkinci parametre *varColor*, denetime uygulamak için renk tanımlar.

## <a name="calling-c-code-in-the-html-file"></a>HTML dosyasında C++ kodu çağırma

Üstbilgi dosyasında WebBrowser yöntemleri bildirdikten sonra HTML dosyasından yöntemlerini çağırabilirsiniz. ATL Denetim Sihirbazı'nı üç Windows Dağıtım yöntemleri ekler olduğuna dikkat edin HTML dosyası: üç `OnClick` denetimin arka plan rengini değiştirmek için iletileri gönderme yöntemleri.

HTML dosyasındaki yöntemlerden birini inceleyin:

`<BUTTON onclick='window.external.OnClick(theBody, "red");'>Red</BUTTON>`

HTML kod penceresi dış yöntem yukarıda `OnClick`, düğmesi etiketinin bir parçası olarak çağırılır. Yöntemi iki parametreye sahiptir: `theBody`, HTML belge gövdesinin başvuruyor ve `"red"`, düğme tıklandığında denetimin arka plan rengi kırmızı değiştirilecek gösterir. `Red` Etiketi aşağıdaki olan düğmenin etiket.

Bkz: [ATL DHTML denetimini değiştirme](../atl/modifying-the-atl-dhtml-control.md) kendi yöntemleri sağlama hakkında daha fazla bilgi için. Bkz: [DHTML denetim projesinin öğelerini tanımlama](../atl/identifying-the-elements-of-the-dhtml-control-project.md) HTML dosyası hakkında daha fazla bilgi.

## <a name="see-also"></a>Ayrıca bkz.

[DHTML denetimi için destek](../atl/atl-support-for-dhtml-controls.md)
