---
description: 'Daha fazla bilgi edinin: ATL DHTML denetimini değiştirme'
title: ATL DHTML denetimini değiştirme
ms.date: 11/04/2016
helpviewer_keywords:
- HTML controls, modifying
- DHTML controls
- DHTML controls, modifying
ms.assetid: c053f35f-8629-4600-9595-721f5956777a
ms.openlocfilehash: 7ae9c102addd7a33341a8f16105a3581de10481e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97159459"
---
# <a name="modifying-the-atl-dhtml-control"></a>ATL DHTML denetimini değiştirme

ATL Denetim Sihirbazı, denetimi derleyip çalıştırmak için başlangıç kodu sağlar ve bu sayede yöntemlerin proje dosyalarında nasıl yazıldığını ve dağıtım yöntemlerini kullanarak, DHTML 'nin denetimin C++ kodunu nasıl çağırdıkları hakkında bilgi alabilirsiniz. Arayüze herhangi bir dağıtım yöntemi ekleyebilirsiniz. Daha sonra, HTML kaynağındaki yöntemleri çağırabilirsiniz.

## <a name="to-modify-the-atl-dhtml-control"></a>ATL DHTML denetimini değiştirmek için

1. **Sınıf görünümü**, denetim projesini genişletin.

   "UI" ile biten arabirimin tek bir yöntemi olduğunu unutmayın `OnClick` . "UI" içinde bitolmayan arabirimin yöntemi yok.

1. `MethodInvoked`Arabirimine, "UI" ile bitmez adlı bir yöntem ekleyin.

   Bu yöntem, bir denetim ile etkileşim kurmak için DHTML tarafından kullanılan arabirime değil, kapsayıcı etkileşimi için denetim kapsayıcısında kullanılan arabirime eklenecektir. Yalnızca kapsayıcı bu yöntemi çağırabilir.

1. . Cpp dosyasında saplaması-Out yöntemini bulun ve bir ileti kutusu göstermek için kod ekleyin, örneğin:

   [!code-cpp[NVC_ATL_COM#5](../atl/codesnippet/cpp/modifying-the-atl-dhtml-control_1.cpp)]

1. Yalnızca bu kez adlı başka bir yöntem ekleyin, `HelloHTML` bunu "UI" ile biten arabirime ekleyin. `HelloHTML`. Cpp dosyasında saplaması-Out yöntemini bulun ve bir ileti kutusu göstermek için kod ekleyin, örneğin:

   [!code-cpp[NVC_ATL_COM#6](../atl/codesnippet/cpp/modifying-the-atl-dhtml-control_2.cpp)]

1. "UI" ile bitolmayan arabirime üçüncü bir yöntem ekleyin `GoToURL` . Bu yöntemi, aşağıdaki gibi [denetiminden IWebBrowser2:: gezinmek](/previous-versions//aa752133\(v=vs.85\))öğesini çağırarak uygulayın:

   [!code-cpp[NVC_ATL_COM#7](../atl/codesnippet/cpp/modifying-the-atl-dhtml-control_3.cpp)]

   `IWebBrowser2`ATL,. h dosyanızda sizin için bu arabirime bir işaretçi sağladığından bu yöntemleri kullanabilirsiniz.

Sonra, oluşturduğunuz yöntemleri çağırmak için HTML kaynağını değiştirin. Bu yöntemleri çağırmak için üç düğme ekleyeceksiniz.

## <a name="to-modify-the-html-resource"></a>HTML kaynağını değiştirmek için

1. **Çözüm Gezgini**, HTML kaynağını göstermek için. htm dosyasına çift tıklayın.

   Özellikle dış Windows Dağıtım yöntemlerine yapılan çağrıları HTML olarak inceleyin. HTML, projenin `OnClick` yöntemini çağırır ve parametreler denetimin gövdesini ( `theBody` ) ve atanacak rengi (" `red` ") gösterir. Yöntem çağrısını izleyen metin, düğmesinde görüntülenen etikettir.

1. Başka bir `OnClick` Yöntem ekleyin, yalnızca rengi değiştirin. Örneğin:

    ```html
    <br>
    <br>
    <BUTTON onclick='window.external.OnClick(theBody, "white");'>Refresh</BUTTON>
    ```

   Bu yöntem, kullanıcının denetimi özgün, beyaz arka plana döndürmek için tıklazecek şekilde, **Yenile** etiketli bir düğme oluşturur.

1. Çağrıyı `HelloHTML` oluşturduğunuz yönteme ekleyin. Örneğin:

    ```html
    <br>
    <br>
    <BUTTON onclick='window.external.HelloHTML();'>HelloHTML</BUTTON>
    ```

   Bu yöntem, kullanıcının ileti kutusunu görüntülemesi için tıkla, **Merhaba HTML** etiketli bir düğme oluşturur `HelloHTML` .

Artık [DEĞIŞTIRILEN DHTML denetimini](../atl/testing-the-modified-atl-dhtml-control.md)oluşturabilir ve test edebilirsiniz.

## <a name="see-also"></a>Ayrıca bkz.

[DHTML denetimi desteği](../atl/atl-support-for-dhtml-controls.md)
