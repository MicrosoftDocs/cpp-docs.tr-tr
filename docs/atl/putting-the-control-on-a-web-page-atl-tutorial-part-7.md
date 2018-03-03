---
title: "Bir Web sayfası (ATL Eğitmeni, Bölüm 7) denetimi koyma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: get-started-article
dev_langs:
- C++
ms.assetid: 50dc4c95-c95b-4006-b88a-9826f7bdb222
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 523086c70d9f974c014f5d33a71bf9309b8e017d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="putting-the-control-on-a-web-page-atl-tutorial-part-7"></a>Denetimi Web Sayfasına Koyma (ATL Eğitmeni, Bölüm 7)
Denetim şimdi tamamlandı. Gerçek dünya durumda işe denetiminizi görmek için bir Web sayfasında yerleştirin. Denetim tanımlandığında denetimi içeren bir HTML dosyası oluşturuldu. PolyCtl.htm dosyadan Aç **Çözüm Gezgini**, bir Web sayfası denetiminizde görebilirsiniz.  
  
 Bu adımda, olaylarını yanıtlamak için Web sayfası komut dosyası. Ayrıca, Internet Explorer denetimi komut dosyası için güvenli olduğunu bildiğiniz izin vermek için Denetim değiştirecektir.  
  
## <a name="scripting-the-web-page"></a>Web sayfası komut dosyası oluşturma  
 Denetim bir şey yapmanız henüz, böylece gönderdiğiniz olaylarını yanıtlamak için Web sayfasını değiştirme.  
  
#### <a name="to-script-the-web-page"></a>Komut dosyası Web sayfası  
  
1.  PolyCtl.htm açın ve HTML görünümü seçin. HTML kodunda aşağıdaki satırları ekleyin. Sonra eklenmelidir `</OBJECT>` önce `</BODY>`.  
  
 ```  
 
 <SCRIPT LANGUAGE="VBScript">  
 <!--  
    Sub PolyCtl_ClickIn(x, y)  
    PolyCtl.Sides = PolyCtl.Sides + 1  
    End Sub  
    Sub PolyCtl_ClickOut(x, y)  
    PolyCtl.Sides = PolyCtl.Sides - 1  
    End Sub  
 -->  
 </SCRIPT>  
 ```  
  
2.  HTM dosyasını kaydedin.  
  
 Denetimden kenara özelliğini alır ve içindeki denetim tıklatırsanız kenar sayısını bir azaltır bazı VBScript kodu eklemiştir. Dışında denetimi tıklatırsanız, kenar sayısını bir azaltır.  
  
## <a name="indicating-that-the-control-is-safe-for-scripting"></a>Denetim komut dosyası için güvenli olduğunu belirten  
 Internet Explorer'da Web sayfası denetimi ile görüntüleyebilirsiniz ya da daha rahat, Visual C++ yerleşik Web tarayıcısı görünümünü kullanın. Web tarayıcısı görünümünde denetim görmek için PolyCtl.htm sağ tıklatın ve'ı tıklatın **tarayıcıda görüntüle**.  
  
 Geçerli Internet Explorer güvenlik ayarlarınızı temel alan, Güvenlik Uyarısı iletişim kutusu denetim komut dosyası için güvenli olmayabilir ve potansiyel olarak verebilir belirten zarar alabilirsiniz. Örneğin, bir dosya görüntülenen ancak de sahip bir denetim varsa bir `Delete` silinen bir dosya yöntemi, onu olacaktır güvenli yalnızca bir sayfa üzerinde görüntülenirse. Birisi çağırabilirsiniz olduğundan bu komut, ancak güvenli olmayacaktır `Delete` yöntemi.  
  
> [!IMPORTANT]
>  Bu öğretici için güvenli olarak işaretlenmemiş ActiveX denetimlerini çalıştırmak için Internet Explorer'da, güvenlik ayarlarını değiştirebilirsiniz. Denetim Masası'nda tıklatın **Internet Özellikleri** tıklatıp **güvenlik** uygun ayarları değiştirmek için. Öğreticiyi tamamladıktan sonra özgün durumlarına güvenlik ayarlarınızı değiştirin.  
  
 Internet Explorer belirli bu denetim için Güvenlik Uyarısı iletişim kutusu görüntülemek gerekmez program aracılığıyla uyarabilir. Bunu yapmak `IObjectSafety` arabirimi ve ATL sağlayan sınıfı bu arabirimi uygulaması [IObjectSafetyImpl](../atl/reference/iobjectsafetyimpl-class.md). Denetiminize arabirimi eklemek için Ekle `IObjectSafetyImpl` listenize devralınan sınıfların ve COM eşlemesinde için bir giriş ekleyin.  
  
#### <a name="to-add-iobjectsafetyimpl-to-the-control"></a>IObjectSafetyImpl denetimine eklemek için  
  
1.  PolyCtl.h devralınan sınıflarda listesinin sonuna aşağıdaki satırı ekleyin ve önceki satıra virgül ekleyin:  
  
 [!code-cpp[NVC_ATL_Windowing#62](../atl/codesnippet/cpp/putting-the-control-on-a-web-page-atl-tutorial-part-7_1.h)]  
  
2.  PolyCtl.h COM eşlemesinde aşağıdaki satırı ekleyin:  
  
 [!code-cpp[NVC_ATL_Windowing#63](../atl/codesnippet/cpp/putting-the-control-on-a-web-page-atl-tutorial-part-7_2.h)]  
  
## <a name="building-and-testing-the-control"></a>Derleme ve denetim test etme  
 Denetim oluşturun. Yapı tamamlandıktan sonra PolyCtl.htm tarayıcı görünümünde yeniden açın. Bu süre, doğrudan Güvenlik Uyarısı iletişim kutusu Web sayfasının görüntülenmesi gerekir. Çokgen tıklatın; kenar sayısını bir azaltır. Kenar sayısını azaltmak için Çokgen dışında'ı tıklatın. Üç aşağıda kenar sayısını azaltmak çalışırsanız, ayarladığınız hata iletisi görürsünüz.  
  
 [6. adıma geri](../atl/adding-a-property-page-atl-tutorial-part-6.md)  
  
## <a name="next-steps"></a>Sonraki Adımlar  
 ATL öğretici sonlanır. ATL hakkında daha fazla bilgi için bağlantılar için bkz: [ATL başlangıç sayfasının](../atl/active-template-library-atl-concepts.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Öğretici](../atl/active-template-library-atl-tutorial.md)

