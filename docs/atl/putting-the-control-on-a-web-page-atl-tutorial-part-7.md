---
description: 'Hakkında daha fazla bilgi edinin: denetimi bir Web sayfasına koyma (ATL öğreticisi, Bölüm 7)'
title: Denetimi Web Sayfasına Koyma (ATL Eğitmeni, Bölüm 7)
ms.custom: get-started-article
ms.date: 05/06/2019
ms.assetid: 50dc4c95-c95b-4006-b88a-9826f7bdb222
ms.openlocfilehash: 738d847a6436a2afab2e336502ec3255d1a1e589
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97159186"
---
# <a name="putting-the-control-on-a-web-page-atl-tutorial-part-7"></a>Denetimi Web Sayfasına Koyma (ATL Eğitmeni, Bölüm 7)

Denetiminiz artık bitmiş. Denetiminizin gerçek dünyada çalıştığını görmek için, bir Web sayfasına koyun. Denetiminizi tanımladığınızda denetimi içeren bir HTML dosyası oluşturuldu. **Çözüm Gezgini** PolyCtl.htm dosyasını açın ve denetiminizi bir Web sayfasında görebilirsiniz.

Bu adımda, olaylara yanıt vermek için denetime işlevsellik ekler ve Web sayfasını betiğe olursunuz. Ayrıca, denetimi Internet Explorer 'ın komut dosyası oluşturma için güvenli olduğunu bilmesini sağlamak için de değiştirebilirsiniz.

## <a name="adding-new-functionality"></a>Yeni işlevsellik ekleme

### <a name="to-add-control-features"></a>Denetim özellikleri eklemek için

1. PolyCtl. cpp ' i açın ve aşağıdaki kodu değiştirin:

    ```cpp
    if (PtInRegion(hRgn, xPos, yPos))
        Fire_ClickIn(xPos, yPos);
    else
        Fire_ClickOut(xPos, yPos);
    ```

    örneklerini şununla değiştirin:

    ```cpp
    short temp = m_nSides;
    if (PtInRegion(hRgn, xPos, yPos))
    {
        Fire_ClickIn(xPos, yPos);
        put_Sides(++temp);
    }
    else
    {
        Fire_ClickOut(xPos, yPos);
        put_Sides(--temp);
    }
    ```

Şekil şimdi, nereye tıkladığınıza bağlı olarak kenar ekler veya kaldırır.

## <a name="scripting-the-web-page"></a>Web sayfasını betik oluşturma

Denetim henüz bir şey yapmaz, bu nedenle Web sayfasını, göndereceğiniz olaylara yanıt verecek şekilde değiştirin.

### <a name="to-script-the-web-page"></a>Web sayfasına betik eklemek için

1. PolyCtl.htm açın ve HTML görünümü ' nü seçin. Aşağıdaki satırları HTML koduna ekleyin. Bunlar, öğesinden sonra eklenmelidir `</OBJECT>` `</BODY>` .

    ```html
    <SCRIPT LANGUAGE="VBScript">
    <!--
        Sub PolyCtl_ClickIn(x, y)
            MsgBox("Clicked (" & x & ", " & y & ") - adding side")
        End Sub
        Sub PolyCtl_ClickOut(x, y)
            MsgBox("Clicked (" & x & ", " & y & ") - removing side")
        End Sub
    -->
    </SCRIPT>
    ```

1. HTM dosyasını kaydedin.

Denetimden yüz özelliğini alan VBScript kodu eklediniz. Denetimin içine tıkladığınızda kenar sayısını bir artırır. Denetimin dışını tıklatırsanız, yüz sayısını bir tane azaltırsınız.

## <a name="indicating-that-the-control-is-safe-for-scripting"></a>Denetimin komut dosyası oluşturma için güvenli olduğunu belirtir

Web sayfasını yalnızca Internet Explorer 'daki denetimle görüntüleyebilirsiniz. Güvenlik zayıflığı nedeniyle diğer tarayıcılar artık ActiveX denetimlerini desteklemez.

> [!NOTE]
> Denetim görünür değilse, bazı tarayıcıların ActiveX denetimlerini çalıştırmak için ayar ayarlamaları gerektirdiğini öğrenin. ActiveX denetimlerinin nasıl etkinleştirileceği hakkında daha fazla bilgi için tarayıcıya bakın.

Geçerli Internet Explorer Güvenlik ayarlarınıza göre, bir güvenlik uyarısı iletişim kutusu alabilirsiniz. Denetimin betik için güvenli olamayacağını ve muhtemelen hasar olabileceğini belirtir. Örneğin, bir dosyayı görüntüleyen ancak aynı zamanda bir dosyayı silen bir yönteme sahip olsaydıysanız `Delete` , bir sayfada yalnızca görüntüleniyorsa güvenli hale gelir. Ancak, bir Kullanıcı yöntemi çağırabileceğinden, komut dosyası için güvenli olmaz `Delete` .

> [!IMPORTANT]
> Bu öğreticide, güvenli olarak işaretlenmemiş ActiveX denetimlerini çalıştırmak için Internet Explorer 'daki güvenlik ayarlarını değiştirebilirsiniz. Denetim Masası 'nda **Internet özellikleri** ' ne tıklayın ve uygun ayarları değiştirmek için **güvenlik** ' e tıklayın. Öğreticiyi tamamladığınızda, güvenlik ayarlarınızı özgün durumlarına geri çevirin.

Internet Explorer 'a, bu belirli denetim için güvenlik uyarısı iletişim kutusunu görüntülemesi gerekmediğini program aracılığıyla uyarabilir. Bunu arabirimini kullanarak yapabilirsiniz `IObjectSafety` . ATL, [IObjectSafetyImpl](../atl/reference/iobjectsafetyimpl-class.md)sınıfında bu arabirimin bir uygulamasını sağlar. Denetimi denetime eklemek için, `IObjectSafetyImpl` devralınan sınıflar listenize ekleyin ve com haritanızda buna bir giriş ekleyin.

### <a name="to-add-iobjectsafetyimpl-to-the-control"></a>Denetime IObjectSafetyImpl eklemek için

1. PolyCtl. h içindeki devralınan sınıfların listesinin sonuna aşağıdaki satırı ekleyin ve önceki satıra bir virgül ekleyin:

    [!code-cpp[NVC_ATL_Windowing#62](../atl/codesnippet/cpp/putting-the-control-on-a-web-page-atl-tutorial-part-7_1.h)]

1. PolyCtl. h içindeki COM eşlemesine aşağıdaki satırı ekleyin:

    [!code-cpp[NVC_ATL_Windowing#63](../atl/codesnippet/cpp/putting-the-control-on-a-web-page-atl-tutorial-part-7_2.h)]

## <a name="building-and-testing-the-control"></a>Denetim oluşturma ve test etme

Denetimi oluşturun. Derleme tamamlandıktan sonra tarayıcı görünümünde PolyCtl.htm tekrar açın. Bu kez, Web sayfası doğrudan **güvenlik uyarısı** iletişim kutusu olmadan görüntülenmelidir. Çokgenin içine tıkladığınızda kenar sayısı bir artar. Kenar sayısını azaltmak için çokgenin dışına tıklayın.

[6. adıma dön](../atl/adding-a-property-page-atl-tutorial-part-6.md)

## <a name="next-steps"></a>Sonraki Adımlar

Bu adım, ATL öğreticisini sonlanır. ATL hakkında daha fazla bilgi için bkz. [ATL başlangıç sayfası](../atl/active-template-library-atl-concepts.md).

## <a name="see-also"></a>Ayrıca bkz.

[Öğretici](../atl/active-template-library-atl-tutorial.md)
