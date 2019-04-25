---
title: ATL DHTML denetimini değiştirme
ms.date: 11/04/2016
helpviewer_keywords:
- HTML controls, modifying
- DHTML controls
- DHTML controls, modifying
ms.assetid: c053f35f-8629-4600-9595-721f5956777a
ms.openlocfilehash: 6c8976c013d0114a3115d3b0bc38fa4bc6acb5b7
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62261663"
---
# <a name="modifying-the-atl-dhtml-control"></a>ATL DHTML denetimini değiştirme

ATL denetimi Sihirbazı, yapı ve denetim çalıştırın ve proje dosyalarında yöntemleri nasıl yazılır ve DHTML denetim C++ koduna dağıtma yöntemleri kullanarak çağırması görebilmeniz için Başlatıcı kodu sağlar. Herhangi bir gönderme yöntemi arabirimi ekleyebilirsiniz. Ardından, HTML kaynak yöntemleri çağırabilir.

## <a name="to-modify-the-atl-dhtml-control"></a>ATL DHTML denetimini değiştirme

1. İçinde **sınıf görünümü**, denetimi projeyi genişletin.

   "Kullanıcı Arabiriminde" ile biten arabirimi bir yöntem olduğunu Not `OnClick`. "Kullanıcı Arabiriminde" bitmiyor arabirimi herhangi bir yöntem yok.

1. Adlı bir yöntem ekleyin `MethodInvoked` "Kullanıcı Arabiriminde." bitmiyor arabirimi

   Bu yöntem denetim kapsayıcısında tarafından DHTML denetimi ile etkileşim kurmak için kullanılan arabirimi kapsayıcı etkileşim için kullanılan arabirimi eklenir. Kapsayıcı yalnızca bu yöntem çağırabilirsiniz.

1. Saplama genişletme yöntemi .cpp dosyasını bulun ve örneğin bir ileti kutusu görüntülemek için kod ekleyin:

   [!code-cpp[NVC_ATL_COM#5](../atl/codesnippet/cpp/modifying-the-atl-dhtml-control_1.cpp)]

1. Adlı başka bir yöntem ekleyin `HelloHTML`, yalnızca bu kez, "Kullanıcı Arabiriminde." ile biten arabirimi ekleme Saplama çıkış Bul `HelloHTML` .cpp yönteminde dosya ve örneğin bir ileti kutusu görüntülemek için kod ekleyin:

   [!code-cpp[NVC_ATL_COM#6](../atl/codesnippet/cpp/modifying-the-atl-dhtml-control_2.cpp)]

1. Üçüncü bir yöntem ekleyin `GoToURL`, "Kullanıcı Arabiriminde." bitmiyor arabirimi Bu yöntemi çağırarak uygulaması [IWebBrowser2::Navigate](https://msdn.microsoft.com/library/aa752133.aspx)gibi:

   [!code-cpp[NVC_ATL_COM#7](../atl/codesnippet/cpp/modifying-the-atl-dhtml-control_3.cpp)]

   Kullanabileceğiniz `IWebBrowser2` yöntemleri çünkü ATL bu arabirim işaretçisi, .h dosyanızda sağlar.

Ardından, oluşturduğunuz yöntemlerini çağırmak için HTML kaynak değiştirin. Bu yöntemleri çağırmak için üç düğmeler ekleyeceksiniz.

## <a name="to-modify-the-html-resource"></a>HTML kaynağı değiştirmek için

1. İçinde **Çözüm Gezgini**, .htm dosyasının, HTML kaynağı görüntülemek için çift tıklayın.

   HTML, özellikle dış Windows gönderme yöntemlere yapılan çağrılar inceleyin. Projenin HTML çağırır `OnClick` yöntemi ve parametreleri belirtmek denetim gövdesi (`theBody`) ve atamak için renk ("`red`"). Yöntem çağrısının metni düğme üzerinde görünen etiketidir.

1. Başka bir `OnClick` yöntemi, yalnızca değişiklik rengi. Örneğin:

    ```html
    <br>
    <br>
    <BUTTON onclick='window.external.OnClick(theBody, "white");'>Refresh</BUTTON>
    ```

   Bu yöntem etiketli bir düğme oluşturur **Yenile**, kullanıcının özgün, beyaz arka plan denetim döndürülecek tıklayabilirsiniz.

1. Çağrısı ekleyin `HelloHTML` oluşturduğunuz yöntemi. Örneğin:

    ```html
    <br>
    <br>
    <BUTTON onclick='window.external.HelloHTML();'>HelloHTML</BUTTON>
    ```

   Bu yöntem etiketli bir düğme oluşturur **HelloHTML**, kullanıcı görüntülemek için tıklayabileceği `HelloHTML` ileti kutusu.

Artık oluşturabilirsiniz ve [değiştirilmiş DHTML denetimini test](../atl/testing-the-modified-atl-dhtml-control.md).

## <a name="see-also"></a>Ayrıca bkz.

[DHTML denetimi için destek](../atl/atl-support-for-dhtml-controls.md)
