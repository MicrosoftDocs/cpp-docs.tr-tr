---
title: Denetimi (ATL Eğitmeni, Bölüm 7) bir Web sayfasına koyma | Microsoft Docs
ms.custom: get-started-article
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 50dc4c95-c95b-4006-b88a-9826f7bdb222
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: edc45522aaff12077de6115105b344ecf41e187e
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/05/2018
ms.locfileid: "43762830"
---
# <a name="putting-the-control-on-a-web-page-atl-tutorial-part-7"></a>Denetimi Web Sayfasına Koyma (ATL Eğitmeni, Bölüm 7)

Denetiminiz artık tamamlandı. Denetim çalışmanızı gerçek durumda görmek için bir Web sayfasına koyun. Denetim tanımladığınızda, denetim içeren bir HTML dosyası oluşturuldu. Nden PolyCtl.htm dosyasını açın **Çözüm Gezgini**, denetiminizi Web sayfasında görebilirsiniz.

Bu adımda, olaylara yanıt vermesi için Web sayfasına komut dosyası eklersiniz. Ayrıca, Internet Explorer'ın denetimin komut dosyası için güvenli olduğunu bilmesini sağlamak için denetimi değiştirir.

## <a name="scripting-the-web-page"></a>Web sayfası betiği oluşturma

Denetim bir şey henüz, dolayısıyla gönderdiğiniz olaylara yanıt vermek için Web sayfasını değiştirin.

#### <a name="to-script-the-web-page"></a>Web sayfası betiği oluşturmak için

1. Polyctl.htm dosyasını açın ve HTML görünümü seçin. Aşağıdaki satırları HTML koduna ekleyin. Sonra eklenmelidir `</OBJECT>` önce `</BODY>`.

    ```html
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

2. HTM dosyasını kaydedin.

Denetimden kenar özelliğini alır ve denetimin içini tıkladığınızda bir kenar sayısını artıran bazı VBScript kodlarını eklediniz. Denetimin dışına tıklarsanız, kenar sayısını birer birer azaltır.

## <a name="indicating-that-the-control-is-safe-for-scripting"></a>Denetim komut dosyası için güvenli olduğunu gösterme

Denetimi içeren Web sayfasını Internet Explorer'da görüntüleyebilir veya daha fazla rahatı, Visual C++ ile oluşturulan Web tarayıcı görünümü kullanın. Denetiminizi Web tarayıcısı görünümünde görmek için polyctl.htm dosyasını sağ tıklayın ve **tarayıcıda görüntüle**.

Geçerli Internet Explorer güvenlik ayarlarınıza göre bağlı olarak, Güvenlik Uyarısı iletişim kutusu denetim komut dosyası için güvenli olmayabilir ve potansiyel olarak verebilir belirten zarar alabilirsiniz. Örneğin, ancak ayrıca bir dosya görüntüleyen bir denetiminizin yanında, bir `Delete` bir dosyayı silen yöntemi olacağını güvenli yalnızca bir sayfa üzerinde görüntülemeniz. Biri çağırabilirsiniz çünkü bu betik, ancak güvenli olmayacaktır `Delete` yöntemi.

> [!IMPORTANT]
> Bu öğretici için güvenli olarak işaretlenmemiş ActiveX denetimlerini çalıştırmak için Internet Explorer'da güvenlik ayarlarını değiştirebilirsiniz. Denetim Masası'nda tıklatın **Internet Özellikleri** tıklatıp **güvenlik** uygun ayarları değiştirmek için. Öğreticiyi tamamladıktan sonra güvenlik ayarlarınızı ilk durumuna değiştirin.

Ayrıca, bu belirli denetim için Güvenlik Uyarısı iletişim kutusunu görüntülemek gerekmeyen Internet Explorer programlı olarak uyarabilir. İle bunu yapabilirsiniz `IObjectSafety` arabirimi ve ATL sağlayan bir uygulama sınıfındaki bu arabirimin [Iobjectsafetyımpl](../atl/reference/iobjectsafetyimpl-class.md). Arabirimi denetiminize eklemek için Ekle `IObjectSafetyImpl` devralınan sınıflar listenize ve bunun için COM haritanıza bir giriş ekleyin.

#### <a name="to-add-iobjectsafetyimpl-to-the-control"></a>Denetime Iobjectsafetyımpl eklemek için

1. PolyCtl.h içindeki devralınmış sınıflar listesinin sonuna aşağıdaki satırı ekleyin ve önceki satıra bir virgül ekleyin:

[!code-cpp[NVC_ATL_Windowing#62](../atl/codesnippet/cpp/putting-the-control-on-a-web-page-atl-tutorial-part-7_1.h)]

2. PolyCtl.h içindeki COM eşlemesine aşağıdaki satırı ekleyin:

[!code-cpp[NVC_ATL_Windowing#63](../atl/codesnippet/cpp/putting-the-control-on-a-web-page-atl-tutorial-part-7_2.h)]

## <a name="building-and-testing-the-control"></a>Derleme ve denetimini test etme

Denetimi oluşturun. Derleme tamamlandıktan sonra polyctl.htm dosyasını tarayıcı görünümünde yeniden açın. Bu kez Web sayfası doğrudan Güvenlik Uyarısı iletişim kutusu görüntülenmesi gerekir. Çokgenin tıklayın; kenar sayısını birer birer artırır. Kenar sayısını azaltmak için çokgenin dışını tıklayın. Üçten sayısını azaltmak çalışırsanız, ayarladığınız hata iletisini görürsünüz.

[6. adıma geri](../atl/adding-a-property-page-atl-tutorial-part-6.md)

## <a name="next-steps"></a>Sonraki Adımlar

Bu, ATL Öğreticisi burada sona eriyor. ATL hakkında daha fazla bilgi için bağlantılar için bkz: [ATL başlangıç sayfası](../atl/active-template-library-atl-concepts.md).

## <a name="see-also"></a>Ayrıca Bkz.

[Öğretici](../atl/active-template-library-atl-tutorial.md)
