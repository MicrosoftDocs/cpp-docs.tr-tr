---
title: ATL DHTML denetimini değiştirme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- HTML controls, modifying
- DHTML controls
- DHTML controls, modifying
ms.assetid: c053f35f-8629-4600-9595-721f5956777a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4a0652ca867ba49243ca5c87caa1dec98da929cf
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/05/2018
ms.locfileid: "43764556"
---
# <a name="modifying-the-atl-dhtml-control"></a>ATL DHTML denetimini değiştirme

ATL denetimi Sihirbazı, yapı ve denetim çalıştırın ve proje dosyalarında yöntemleri nasıl yazılır ve DHTML denetim C++ koduna dağıtma yöntemleri kullanarak çağırması görebilmeniz için Başlatıcı kodu sağlar. Herhangi bir gönderme yöntemi arabirimi ekleyebilirsiniz. Ardından, HTML kaynak yöntemleri çağırabilir.

#### <a name="to-modify-the-atl-dhtml-control"></a>ATL DHTML denetimini değiştirme

1. Sınıf Görünümü'nde denetimi projeyi genişletin.

   "Kullanıcı Arabiriminde" ile biten arabirimi bir yöntem olduğunu Not `OnClick`. "Kullanıcı Arabiriminde" bitmiyor arabirimi herhangi bir yöntem yok.

2. Adlı bir yöntem ekleyin `MethodInvoked` "Kullanıcı Arabiriminde." bitmiyor arabirimi

   Bu yöntem denetim kapsayıcısında tarafından DHTML denetimi ile etkileşim kurmak için kullanılan arabirimi kapsayıcı etkileşim için kullanılan arabirimi eklenir. Kapsayıcı yalnızca bu yöntem çağırabilirsiniz.

3. Saplama genişletme yöntemi .cpp dosyasını bulun ve örneğin bir ileti kutusu görüntülemek için kod ekleyin:

   [!code-cpp[NVC_ATL_COM#5](../atl/codesnippet/cpp/modifying-the-atl-dhtml-control_1.cpp)]

4. Adlı başka bir yöntem ekleyin `HelloHTML`, yalnızca bu kez, "Kullanıcı Arabiriminde." ile biten arabirimi ekleme Saplama çıkış Bul `HelloHTML` .cpp yönteminde dosya ve örneğin bir ileti kutusu görüntülemek için kod ekleyin:

   [!code-cpp[NVC_ATL_COM#6](../atl/codesnippet/cpp/modifying-the-atl-dhtml-control_2.cpp)]

5. Üçüncü bir yöntem ekleyin `GoToURL`, "Kullanıcı Arabiriminde." bitmiyor arabirimi Bu yöntemi çağırarak uygulaması [IWebBrowser2::Navigate](https://msdn.microsoft.com/library/aa752133.aspx)gibi:

   [!code-cpp[NVC_ATL_COM#7](../atl/codesnippet/cpp/modifying-the-atl-dhtml-control_3.cpp)]

   Kullanabileceğiniz **Iwebbrowser2** yöntemleri çünkü ATL bu arabirim işaretçisi, .h dosyanızda sağlar.

Ardından, oluşturduğunuz yöntemlerini çağırmak için HTML kaynak değiştirin. Bu yöntemleri çağırmak için üç düğmeler ekleyeceksiniz.  

#### <a name="to-modify-the-html-resource"></a>HTML kaynağı değiştirmek için

1. Çözüm Gezgini'nde .htm dosyasının, HTML kaynağı görüntülemek için çift tıklayın.

   HTML, özellikle dış Windows gönderme yöntemlere yapılan çağrılar inceleyin. Projenin HTML çağırır `OnClick` yöntemi ve parametreleri belirtmek denetim gövdesi (`theBody`) ve atamak için renk ("`red`"). Yöntem çağrısının metni düğme üzerinde görünen etiketidir.

2. Başka bir `OnClick` yöntemi, yalnızca değişiklik rengi. Örneğin:

    ```html
    <br>
    <br>
    <BUTTON onclick='window.external.OnClick(theBody, "white");'>Refresh</BUTTON>
    ```

   Bu yöntem etiketli bir düğme oluşturur **Yenile**, kullanıcının özgün, beyaz arka plan denetim döndürülecek tıklayabilirsiniz.

3. Çağrısı ekleyin `HelloHTML` oluşturduğunuz yöntemi. Örneğin:

    ```html
    <br>  
    <br>  
    <BUTTON onclick='window.external.HelloHTML();'>HelloHTML</BUTTON>  
    ```

   Bu yöntem etiketli bir düğme oluşturur **HelloHTML**, kullanıcı görüntülemek için tıklayabileceği `HelloHTML` ileti kutusu.

Artık oluşturabilirsiniz ve [değiştirilmiş DHTML denetimini test](../atl/testing-the-modified-atl-dhtml-control.md).

## <a name="see-also"></a>Ayrıca Bkz.

[DHTML denetimi için destek](../atl/atl-support-for-dhtml-controls.md)
