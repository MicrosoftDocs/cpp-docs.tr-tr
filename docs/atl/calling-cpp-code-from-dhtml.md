---
description: "Hakkında daha fazla bilgi edinin: DHTML 'den C++ kodu çağırma"
title: DHTML 'den C++ kodu çağırma
ms.date: 11/04/2016
helpviewer_keywords:
- DHTML, calling C++ code from
ms.assetid: 37329acd-4c22-40ca-a85a-b7480748f75f
ms.openlocfilehash: d880b0e9cb2f0b9d5228df7da4fc96fceeb87943
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97148492"
---
# <a name="calling-c-code-from-dhtml"></a>DHTML 'den C++ kodu çağırma

DHTML denetimi, test kapsayıcısı veya Internet Explorer gibi bir kapsayıcıda barındırılabilir. Test kapsayıcısına erişme hakkında bilgi için bkz. test [kapsayıcısı Ile özellikleri ve olayları test etme](../mfc/testing-properties-and-events-with-test-container.md) .

Denetimi barındıran kapsayıcı, normal denetim arabirimlerini kullanarak denetimle iletişim kurar. DHTML, C++ kodunuz ve HTML kaynağınız ile iletişim kurmak için "UI" ile biten dağıtım arabirimini kullanır. [Atl dhtml denetimini değiştirirken](../atl/modifying-the-atl-dhtml-control.md)bu farklı arabirimler tarafından çağrılacak yöntemleri ekleme alıştırması yapabilirsiniz.

DHTML 'den C++ kodu çağırma örneği görmek için, ATL Denetim Sihirbazı 'Nı kullanarak [BIR dhtml denetimi oluşturun](../atl/creating-an-atl-dhtml-control.md) ve üstbilgi DOSYASıNDAKI ve HTML dosyasındaki kodu inceleyin.

## <a name="declaring-webbrowser-methods-in-the-header-file"></a>Üst bilgi dosyasında WebBrowser yöntemleri bildirme

C++ yöntemlerini DHTML kullanıcı arabiriminden çağırmak için, Denetiminizin UI arabirimine Yöntemler eklemeniz gerekir. Örneğin, ATL Denetim Sihirbazı tarafından oluşturulan üstbilgi dosyası `OnClick` , sihirbaz tarafından oluşturulan DENETIMIN UI arabiriminin bir üyesi olan C++ yöntemini içerir.

`OnClick`Denetimin. h dosyasında inceleyin:

[!code-cpp[NVC_ATL_COM#4](../atl/codesnippet/cpp/calling-cpp-code-from-dhtml_1.h)]

İlk parametre olan *pdispBody*, gövde nesnesinin gönderme arabiriminin bir işaretçisidir. *VarColor* ikinci parametresi, denetime uygulanacak rengi tanımlar.

## <a name="calling-c-code-in-the-html-file"></a>HTML dosyasında C++ kodunu çağırma

Üst bilgi dosyasında WebBrowser yöntemlerini bildirdikten sonra, HTML dosyasından yöntemleri çağırabilirsiniz. HTML dosyasında, ATL Denetim Sihirbazı 'nın üç Windows dağıtım yöntemi eklediğine dikkat edin: `OnClick` denetimin arka plan rengini değiştirmek için ileti veren üç yöntem.

HTML dosyasındaki yöntemlerden birini inceleyin:

`<BUTTON onclick='window.external.OnClick(theBody, "red");'>Red</BUTTON>`

Yukarıdaki HTML kodunda, Window dış yöntemi `OnClick` düğme etiketinin bir parçası olarak çağırılır. Yöntemi iki parametreye sahiptir: `theBody` , HTML belgesi gövdesine başvurur ve `"red"` düğme tıklandığında denetimin arka plan renginin kırmızı olarak değiştirildiğini gösterir. `Red`Düğmenin etiketi aşağıdaki etikettir.

Kendi yöntemlerinizi sağlama hakkında daha fazla bilgi için bkz. [atl dhtml denetimini değiştirme](../atl/modifying-the-atl-dhtml-control.md) . HTML dosyası hakkında daha fazla bilgi için bkz. [DHTML denetim projesinin öğelerini tanımlama](../atl/identifying-the-elements-of-the-dhtml-control-project.md) .

## <a name="see-also"></a>Ayrıca bkz.

[DHTML denetimi desteği](../atl/atl-support-for-dhtml-controls.md)
