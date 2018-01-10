---
title: "DHTML denetimi proje öğelerini tanımlama | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- HTML controls, ATL support
- DHTML controls, ATL support
ms.assetid: b627547a-3768-4346-9900-4b7a21fb8e27
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 74b271f56fe7c8d3345ce53de06a18a2700175f2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="identifying-the-elements-of-the-dhtml-control-project"></a>DHTML denetimi proje öğelerini tanımlama
Çoğu DHTML denetim kodu tam olarak gibi diğer herhangi bir ATL denetimi için oluşturulur. Aracılığıyla genel kod temel anlamak için iş [ATL öğretici](../atl/active-template-library-atl-tutorial.md), ve bölümleri okuyun [bir ATL projesi oluşturma](../atl/reference/creating-an-atl-project.md) ve [ATL COM nesneleri Temelleri](../atl/fundamentals-of-atl-com-objects.md).  
  
 DHTML denetimi herhangi bir ATL denetimi için benzer dışında:  
  
-   Bir denetim uygulayan normal arabirimleri yanı sıra HTML kullanıcı arabirimi (UI) ile C++ kodu arasında iletişim kurmak için kullanılan bir ek arabirimi uygular. HTML UI bu arabirimi kullanarak C++ kodu çağırır.  
  
-   UI denetim için bir HTML kaynağı oluşturur.  
  
-   DHTML nesne modeli üye değişkeni aracılığıyla erişmesini sağlar `m_spBrowser`, akıllı bir işaretçi türü olduğu [Iwebbrowser2](https://msdn.microsoft.com/library/aa752127.aspx). DHTML nesne modeli herhangi bir kısmını erişmek için bu işaretçiyi kullanın.  
  
 Aşağıdaki grafikte, DLL, DHTML denetimi, Web tarayıcısı ve HTML kaynağı arasındaki ilişki gösterilmektedir.  
  
 ![DHTML denetimi proje öğelerini](../atl/media/vc52en1.gif "vc52en1")  
  
> [!NOTE]
>  Bu grafikte yer tutucuları adlardır. HTML kaynağınız ve denetiminizi sergilenen arabirimlerle adları ATL Denetim Sihirbazı'nda atamak adları dayanır.  
  
 Bu grafikte öğeler şunlardır:  
  
-   **My DLL** ATL Proje Sihirbazı kullanılarak oluşturulan DLL.  
  
-   **DHTML denetimi** (`m_spBrowser`) ATL nesnesi Sihirbazı kullanılarak oluşturulan DHTML denetimi. Bu denetim Web tarayıcısı nesnenin arabirimi aracılığıyla Web tarayıcısı nesnesi ve yöntemlerinden erişir **Iwebbrowser2**. Denetim bir denetim için gerekli diğer standart arabirimler ek olarak aşağıdaki iki arabirim sunar.  
  
    -   **IDHCTL1** yalnızca kapsayıcı tarafından kullanılmak üzere denetim tarafından sunulan arabirimi.  
  
    -   **IDHCTLUI1** C++ kodu ve HTML kullanıcı arabirimi arasında iletişim için kullanılan gönderme arabirimi. Web tarayıcısı denetimin dağıtma arabirimi denetimini görüntülemek için kullanır. Çağırarak bu dağıtma arabirimi çeşitli yöntemleri denetimin kullanıcı arabiriminden çağırabilirsiniz `window.external`, ardından çağırmak için istediğiniz bu gönderme arabirimdeki yöntem adı. Erişim `window.external` bu denetim için kullanıcı Arabirimi oluşturur HTML içindeki komut dosyası etiketinin gelen. Kaynak dosyasında dış yöntemlerini çağırma hakkında daha fazla bilgi için bkz: [C++ kodundan çağıran DHTML](../atl/calling-cpp-code-from-dhtml.md).  
  
-   **IDR_CTL1** HTML kaynağının kaynak kimliği. Bu durumda, dosya adıyla DHCTL1UI.htm ' dir. DHTML denetimi standart HTML etiketleri ve metin düzenleyicisi kullanarak düzenleyebilirsiniz dış pencere gönderme komutları içeren bir HTML kaynak kullanır.  
  
-   **Web tarayıcısı** Web tarayıcısı denetimin UI, HTML HTML kaynak göre görüntüler. Web tarayıcısının gösteren bir işaretçi **Iwebbrowser2** arabirimidir DHTML denetimi DHTML nesne modeli erişmesine izin vermek için kullanılabilir.  
  
 ATL Denetim Sihirbazı'nı varsayılan kod denetimiyle hem HTML kaynağı hem de .cpp dosyası oluşturur. Derleme ve denetim sihirbaz tarafından oluşturulan gibi çalıştırın ve ardından denetimi Web tarayıcısını veya ActiveX denetimi Test kapsayıcısı içinde görüntüleyin. Aşağıdaki resimde varsayılan ATL DHTML denetimi Test kapsayıcısı görüntülenen üç düğmelerle gösterilmektedir:  
  
 ![ATL DHTML denetimi](../atl/media/vc52en2.gif "vc52en2")  
  
 Bkz: [ATL DHTML denetimi oluşturma](../atl/creating-an-atl-dhtml-control.md) DHTML denetimi oluşturmaya başlamak için. Bkz: [test özellikleri ve olayları Test kapsayıcısı ile](../mfc/testing-properties-and-events-with-test-container.md) Test kapsayıcısı erişim hakkında bilgi için.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [DHTML denetimi için destek](../atl/atl-support-for-dhtml-controls.md)

