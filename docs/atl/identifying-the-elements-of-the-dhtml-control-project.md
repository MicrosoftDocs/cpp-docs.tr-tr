---
title: DHTML denetim projesinin öğelerini tanımlama
ms.date: 11/19/2018
helpviewer_keywords:
- HTML controls, ATL support
- DHTML controls, ATL support
ms.assetid: b627547a-3768-4346-9900-4b7a21fb8e27
ms.openlocfilehash: 3cb250c68d5ba36dc3cf502b871f62eec8f1861c
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57283884"
---
# <a name="identifying-the-elements-of-the-dhtml-control-project"></a>DHTML denetim projesinin öğelerini tanımlama

DHTML denetimi kodların çoğu için herhangi bir ATL denetimi, tam olarak oluşturulur. Genel kod temel bir anlayış için çalışmak [ATL öğretici](../atl/active-template-library-atl-tutorial.md), ve bölümleri okuyun [ATL projesi oluşturma](../atl/reference/creating-an-atl-project.md) ve [ATL COM nesnelerinin Temelleri](../atl/fundamentals-of-atl-com-objects.md).

DHTML denetimi herhangi bir ATL denetimi için benzer hariç:

- Bir denetim uygular normal arabirimlerine ek olarak HTML kullanıcı arabirimi (UI) ve C++ kodu arasında iletişim kurmak için kullanılan ek bir arabirim uygular. HTML kullanıcı Arabirimi bu arabirim kullanarak C++ kodu çağırır.

- Bir HTML kaynak UI denetimi oluşturur.

- DHTML nesne modeli üye değişkeni aracılığıyla erişim sağlayan `m_spBrowser`, akıllı bir işaretçi türünde olduğu [Iwebbrowser2](https://msdn.microsoft.com/library/aa752127.aspx). DHTML nesne modeli, herhangi bir bölümünü erişmek için bu işaretçiyi kullanın.

Aşağıdaki grafikte, DLL, DHTML denetimi, Web tarayıcısı ve HTML kaynak arasındaki ilişkiyi gösterir.

![DHTML denetim projesinin öğelerini](../atl/media/vc52en1.gif "DHTML denetim projesinin öğelerini")

> [!NOTE]
>  Bu grafikte yer tutucuları adlarıdır. Adları, HTML kaynak denetiminizi kullanıma sunulan arabirimler ve ATL denetimi Sihirbazı'nda atama adları temel alır.

Bu grafikte öğeler şunlardır:

- **My DLL** ATL projesi Sihirbazı kullanılarak oluşturulan DLL.

- **DHTML denetimi** (`m_spBrowser`) ATL nesnesi Sihirbazı kullanılarak oluşturulan DHTML denetimi. Bu denetimi Web tarayıcı nesnesi ve metotlarını Web tarayıcı nesnenin arabirimi aracılığıyla erişen `IWebBrowser2`. Denetim, aşağıdaki iki arabirim denetimi için gereken diğer standart arabirimler yanı sıra kullanıma sunar.

   - `IDHCTL1` Yalnızca kapsayıcı tarafından kullanılmak üzere bir denetim tarafından kullanıma sunulan arabirim.

   - `IDHCTLUI1` C++ kodu ve HTML kullanıcı arabirimi arasında iletişim kurmak için gönderme arabirimi. Web tarayıcısı denetimin gönderme arabirimi denetim görüntülemek için kullanır. Bu dağıtım arabirimi çeşitli yöntemleri çağırarak denetimin kullanıcı arabiriminden çağırabilirsiniz `window.external`ve ardından çağırmak istediğiniz bu gönderme arabirimdeki yöntem adı. Erişmek `window.external` gelen bir komut dosyası etiketi oluşturan kullanıcı arabirimini bu denetim için HTML içinde. Kaynak dosyasındaki dış yöntemlerini çağırma hakkında daha fazla bilgi için bkz. [DHTML C++ kodu çağırma](../atl/calling-cpp-code-from-dhtml.md).

- **IDR_CTL1** HTML kaynağının kaynak kimliği. Bu durumda, dosya adını DHCTL1UI.htm ' dir. DHTML denetimi, standart HTML etiketleri ve metin düzenleyicisi kullanarak düzenleyebileceğiniz encerede gönderme komutları içeren bir HTML kaynak kullanır.

- **Web tarayıcısı** Web tarayıcı denetim UI, HTML HTML kaynağında göre görüntüler. Web tarayıcısının bir işaretçiye `IWebBrowser2` arabirimi DHTML denetimi; DHTML nesne modeli erişmesine izin vermek için kullanılabilir.

ATL Denetim Sihirbazı'nı varsayılan kod denetimiyle HTML kaynak ve .cpp dosyası oluşturur. Derleme ve sihirbaz tarafından oluşturulan denetim çalıştırın ve ardından Denetim Web tarayıcısını veya ActiveX denetimi Test kapsayıcısı içinde görüntüleyin. Aşağıdaki resimde varsayılan ATL DHTML denetimini Test kapsayıcısında görüntülenen üç düğme göstermektedir:

![ATL DHTML denetimini](../atl/media/vc52en2.gif "ATL DHTML denetimi")

Bkz: [ATL DHTML denetimi oluşturma](../atl/creating-an-atl-dhtml-control.md) DHTML denetimi oluşturmaya başlamak için. Bkz: [Test kapsayıcısı ile test etme özellikleri ve olayları](../mfc/testing-properties-and-events-with-test-container.md) Test kapsayıcısı erişim hakkında daha fazla bilgi için.

## <a name="see-also"></a>Ayrıca bkz.

[DHTML denetimi için destek](../atl/atl-support-for-dhtml-controls.md)
