---
title: "ATL DHTML denetimi değiştirme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- HTML controls, modifying
- DHTML controls
- DHTML controls, modifying
ms.assetid: c053f35f-8629-4600-9595-721f5956777a
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 74ed32c0322d23cd3da1d439dcc8d8eadb246c13
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="modifying-the-atl-dhtml-control"></a>ATL DHTML denetimi değiştirme
ATL Denetim Sihirbazı'nı Başlatıcı Kodu derlemek ve denetim çalıştırmak için ve yöntemleri proje dosyalarında nasıl yazılır ve nasıl DHTML gönderme yöntemlerini kullanarak denetimin C++ kodu çağırır görebilmeleri sağlar. Herhangi bir gönderme yöntemini arabirimine ekleyebilirsiniz. Ardından, HTML kaynak yöntemleri çağırabilirsiniz.  
  
#### <a name="to-modify-the-atl-dhtml-control"></a>ATL DHTML denetimi değiştirmek için  
  
1.  Sınıf Görünümü'nde denetim projenizi genişletin.  
  
     "Kullanıcı Arabiriminde" ile biten arabirimi bir yöntem, sahip olduğuna dikkat edin `OnClick`. "Kullanıcı Arabiriminde" bitmez arabirimi herhangi bir yöntem yok.  
  
2.  Adlı bir yöntem ekleyin `MethodInvoked` "Kullanıcı Arabiriminde." bitmez arabirimi  
  
     Bu yöntem denetim kapsayıcısında değil tarafından DHTML denetimi ile etkileşim kurmak için kullanılan arabirim için kapsayıcı etkileşim için kullanılan arabirim eklenir. Bu yöntem yalnızca kapsayıcı çağırabilirsiniz.  
  
3.  Tamamlanmamış yöntemi .cpp dosyasını bulun ve örneğin bir ileti kutusu görüntüleme için kodu ekleyin:  
  
 [!code-cpp[NVC_ATL_COM#5](../atl/codesnippet/cpp/modifying-the-atl-dhtml-control_1.cpp)]  
  
4.  Adlı başka bir yöntem ekleyin `HelloHTML`, yalnızca bu kez, "Kullanıcı Arabiriminde." ile biten arabirimi ekleyin Tamamlanmamış çıkış Bul `HelloHTML` .cpp yönteminde dosya ve örneğin bir ileti kutusu görüntüleme için kodu ekleyin:  
  
 [!code-cpp[NVC_ATL_COM#6](../atl/codesnippet/cpp/modifying-the-atl-dhtml-control_2.cpp)]  
  
5.  Üçüncü bir yöntem ekleyin `GoToURL`, "Kullanıcı Arabiriminde." bitmez arabirimi Bu yöntemi çağrılarak uygulaması [IWebBrowser2::Navigate](https://msdn.microsoft.com/library/aa752133.aspx)aşağıdaki gibi:  
  
 [!code-cpp[NVC_ATL_COM#7](../atl/codesnippet/cpp/modifying-the-atl-dhtml-control_3.cpp)]  
  
     Kullanabileceğiniz **Iwebbrowser2** yöntemleri çünkü ATL bu arabirim için bir işaretçi sizin için .h dosyanızda sağlar.  
  
 Ardından, oluşturduğunuz yöntemleri çağırmak için HTML kaynak değiştirin. Bu yöntem çağırma için üç düğme ekleyeceksiniz.  
  
#### <a name="to-modify-the-html-resource"></a>HTML kaynağı değiştirmek için  
  
1.  Çözüm Gezgini'nde, HTML kaynak görüntülenecek .htm dosyasını çift tıklatın.  
  
     HTML, özellikle dış Windows gönderme yöntemlerini çağrıları inceleyin. Projenin HTML çağırır `OnClick` yöntemi ve parametreleri belirtmek denetimi gövdesi (`theBody`) ve atamak için renk ("`red`"). Yöntem çağrısının aşağıdaki düğmeyi görüntülenen etiketi metindir.  
  
2.  Başka bir tane eklemek `OnClick` yöntemi, yalnızca değişikliği rengi. Örneğin:  
  
 ```  
 <br>  
 <br>  
 <BUTTON onclick='window.external.OnClick(theBody, "white");'>Refresh</BUTTON>  
 ```  
  
     Bu yöntem etiketlenmiş bir düğmeyi oluşturacak **yenileme**, kullanıcının özgün, beyaz arka plan denetim döndürülecek tıklatabilirsiniz.  
  
3.  Çağrısı ekleyin `HelloHTML` oluşturduğunuz yöntemi. Örneğin:  
  
 ```  
 <br>  
 <br>  
 <BUTTON onclick='window.external.HelloHTML();'>HelloHTML</BUTTON>  
 ```  
  
     Bu yöntem etiketlenmiş bir düğmeyi oluşturacak **HelloHTML**, kullanıcı görüntülemek için tıklatabileceği `HelloHTML` ileti kutusu.  
  
 Şimdi oluşturabilir ve [değiştirilmiş DHTML denetimi test](../atl/testing-the-modified-atl-dhtml-control.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [DHTML denetimi için destek](../atl/atl-support-for-dhtml-controls.md)

