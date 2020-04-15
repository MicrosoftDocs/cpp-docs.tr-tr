---
title: DHTML Kontrol Projesinin Öğelerinin Belirlenmesi
ms.date: 11/19/2018
helpviewer_keywords:
- HTML controls, ATL support
- DHTML controls, ATL support
ms.assetid: b627547a-3768-4346-9900-4b7a21fb8e27
ms.openlocfilehash: 5fabdc815989c21bdf6b0932b9d6826e28d7012a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81319500"
---
# <a name="identifying-the-elements-of-the-dhtml-control-project"></a>DHTML Kontrol Projesinin Öğelerinin Belirlenmesi

Çoğu DHTML denetim kodu tam olarak herhangi bir ATL denetimi için oluşturulan gibidir. Genel kodun temel bir anlaşılması için, [ATL öğretici](../atl/active-template-library-atl-tutorial.md)ile çalışmak ve [atl com nesnelerin](../atl/fundamentals-of-atl-com-objects.md)bir [ATL Projesi](../atl/reference/creating-an-atl-project.md) ve Temelleri oluşturma bölümleri okuyun.

DHTML denetimi, şu durumlar dışında herhangi bir ATL denetimine benzer:

- Denetimin uyguladığı normal arabirimlere ek olarak, C++ kodu ile HTML kullanıcı arabirimi (UI) arasında iletişim kurmak için kullanılan ek bir arabirim uygular. HTML UI bu arabirimi kullanarak C++ koduna çağırır.

- Denetim UI için bir HTML kaynağı oluşturur.

- Bu üye değişken `m_spBrowser`üzerinden DHTML nesne modeline erişim sağlar , hangi tip [IWebBrowser2](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa752127\(v=vs.85\))akıllı bir işaretçi. DHTML nesne modelinin herhangi bir bölümüne erişmek için bu işaretçiyi kullanın.

Aşağıdaki grafik, DLL, DHTML denetimi, Web tarayıcısı ve HTML kaynağı arasındaki ilişkiyi göstermektedir.

![Bir DHTML kontrol projesinin öğeleri](../atl/media/vc52en1.gif "Bir DHTML kontrol projesinin öğeleri")

> [!NOTE]
> Bu grafikteki adlar yer tutuculardır. HTML kaynağınızın adları ve denetiminizde açığa çıkan arabirimler, ATL Denetim Sihirbazı'nda atadığınız adları temel almaktadır.

Bu grafikte, öğeler şunlardır:

- **Benim DLL** DLL, ATL Proje Sihirbazı kullanılarak oluşturuldu.

- **DHTML** Denetimi`m_spBrowser`( ) ATL Nesne Sihirbazı kullanılarak oluşturulan DHTML denetimi. Bu denetim, Web tarayıcısı nesnesinin arabirimi üzerinden Web `IWebBrowser2`tarayıcısı nesnesine ve yöntemlerine erişir. Denetimin kendisi, denetim için gerekli olan diğer standart arabirimlere ek olarak aşağıdaki iki arabirimi ortaya çıkarır.

  - `IDHCTL1`Yalnızca kapsayıcı tarafından kullanılmak üzere denetim tarafından maruz arayüz.

  - `IDHCTLUI1`C++ kodu ile HTML kullanıcı arabirimi arasında iletişim kurmak için gönderme arabirimi. Web tarayıcısı denetimi görüntülemek için denetimin gönderme arabirimini kullanır. Bu gönderme arabiriminin çeşitli yöntemlerini, çağırmak istediğiniz bu `window.external`gönderi arabirimindeki yöntem adını çağırarak, denetimin kullanıcı arabiriminden arayabilirsiniz. Bu denetim `window.external` için UI'yi oluşturan HTML içindeki bir SCRIPT etiketinden erişebilirsiniz. Kaynak dosyasında dış yöntemleri çağırma hakkında daha fazla bilgi için Bkz. [DHTML'den C++ Kodu Arama.](../atl/calling-cpp-code-from-dhtml.md)

- **IDR_CTL1** HTML kaynağının kaynak kimliği. Dosya adı, bu durumda, DHCTL1UI.htm olduğunu. DHTML denetimi, Metin düzenleyicisini kullanarak ayarlayabileceğiniz standart HTML etiketleri ve harici pencere gönderme komutları içeren bir HTML kaynağı kullanır.

- **Web Tarayıcısı** Web tarayıcısı, HTML kaynağındaki HTML'yi temel alan denetimin UI'sini görüntüler. DHTML nesne modeline `IWebBrowser2` erişimsağlamak için DHTML denetiminde Web tarayıcısının arabirimine işaretçi kullanılabilir.

ATL Denetim Sihirbazı, hem HTML kaynağında hem de .cpp dosyasında varsayılan kodiçeren bir denetim oluşturur. Denetimi sihirbaz tarafından oluşturulan denetimi derleyebilir ve çalıştırabilir ve ardından denetimi Web tarayıcısında veya ActiveX Denetim Test Kapsayıcısı'nda görüntüleyebilirsiniz. Aşağıdaki resimde, Test Kapsayıcısı'nda görüntülenen üç düğmeyle varsayılan ATL DHTML denetimi gösterilmektedir:

![ATL DHTML denetimi](../atl/media/vc52en2.gif "ATL DHTML denetimi")

Bkz. DHTML denetimi oluşturmaya başlamak için [ATL DHTML Denetimi Oluşturma.](../atl/creating-an-atl-dhtml-control.md) Test Kapsayıcısına nasıl erişilisüreceğiniz hakkında bilgi almak için [Test Kapsayıcısı ile Test Özellikleri ve Olayları'na](../mfc/testing-properties-and-events-with-test-container.md) bakın.

## <a name="see-also"></a>Ayrıca bkz.

[DHTML Denetimi desteği](../atl/atl-support-for-dhtml-controls.md)
