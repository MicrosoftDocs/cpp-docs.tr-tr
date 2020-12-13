---
description: 'Hakkında daha fazla bilgi edinin: DHTML denetim projesinin öğelerini tanımlama'
title: DHTML denetim projesinin öğelerini tanımlama
ms.date: 11/19/2018
helpviewer_keywords:
- HTML controls, ATL support
- DHTML controls, ATL support
ms.assetid: b627547a-3768-4346-9900-4b7a21fb8e27
ms.openlocfilehash: 7f04857378564a86fc875e9874b79f6ae6c6a625
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97148024"
---
# <a name="identifying-the-elements-of-the-dhtml-control-project"></a>DHTML denetim projesinin öğelerini tanımlama

Birçok DHTML denetim kodu, tüm ATL denetimleri için oluşturulmuş şekilde tam olarak aynıdır. Genel kodu temel olarak anlamak için, [ATL öğreticisi](../atl/active-template-library-atl-tutorial.md)aracılığıyla çalışın ve ATL [PROJESI oluşturma](../atl/reference/creating-an-atl-project.md) ve [atl com nesnelerinin temelleri](../atl/fundamentals-of-atl-com-objects.md)ile ilgili bölümleri okuyun.

DHTML denetimi aşağıdakiler dışında tüm ATL denetimine benzerdir:

- Bir denetimin uyguladığı normal arabirimlerin yanı sıra, C++ kodu ve HTML Kullanıcı arabirimi (UI) arasında iletişim kurmak için kullanılan ek bir arabirim uygular. HTML Kullanıcı arabirimi bu arabirimi kullanarak C++ koduna çağrı yapılır.

- Denetim Kullanıcı arabirimi için bir HTML kaynağı oluşturur.

- `m_spBrowser` [Denetiminden IWebBrowser2](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa752127\(v=vs.85\))türünde akıllı bir işaretçi olan üye değişkeni aracılığıyla DHTML nesne modeline erişim sağlar. DHTML nesne modelinin herhangi bir bölümüne erişmek için bu işaretçiyi kullanın.

Aşağıdaki grafikte, DLL 'niz, DHTML denetimi, Web tarayıcısı ve HTML kaynağı arasındaki ilişki gösterilmektedir.

![Bir DHTML denetim projesinin öğeleri](../atl/media/vc52en1.gif "Bir DHTML denetim projesinin öğeleri")

> [!NOTE]
> Bu grafikteki adlar yer tutuculardır. HTML kaynağınızın ve denetiminiz üzerinde sunulan arabirimlerin adları, bunları ATL Denetim Sihirbazı 'na atadığınız adlara göre yapılır.

Bu grafikte öğeler şunlardır:

- **My dll** ATL Proje Sihirbazı kullanılarak oluşturulan DLL.

-  `m_spBrowser` ATL nesne Sihirbazı kullanılarak oluşturulan dhtml denetimi () dhtml denetimi. Bu denetim Web tarayıcısı nesnesine ve yöntemlerine Web tarayıcısı nesnesinin arabirimi aracılığıyla erişir `IWebBrowser2` . Denetim, bir denetim için gereken diğer standart arabirimlerin yanı sıra aşağıdaki iki arabirimi de kullanıma sunar.

  - `IDHCTL1` Yalnızca kapsayıcı tarafından kullanılmak üzere denetim tarafından gösterilen arabirim.

  - `IDHCTLUI1` C++ kodu ve HTML Kullanıcı arabirimi arasında iletişim kurmak için dağıtım arabirimi. Web tarayıcısı, denetimi göstermek için denetimin dağıtım arabirimini kullanır. Bunu çağırarak `window.external` , bu dağıtım arabirimindeki yöntemi çağırmak istediğiniz yöntem adını çağırarak, denetimin kullanıcı arabiriminden bu dağıtım arabiriminin çeşitli yöntemlerini çağırabilirsiniz. `window.external`Bu denetim için Kullanıcı arabirimini oluşturan HTML içindeki BIR komut dosyası etiketinden erişirsiniz. Kaynak dosyasında dış yöntemlerin çağrılması hakkında daha fazla bilgi için bkz. [DHTML 'Den C++ kodu çağırma](../atl/calling-cpp-code-from-dhtml.md).

- **IDR_CTL1** HTML kaynağının kaynak KIMLIĞI. Dosya adı bu durumda DHCTL1UI.htm. DHTML denetimi, metin düzenleyicisini kullanarak düzenleyebileceğiniz standart HTML etiketleri ve dış pencere gönderme komutlarını içeren bir HTML kaynağı kullanır.

- **Web tarayıcısı** Web tarayıcısı, HTML kaynağında HTML 'i temel alarak denetimin kullanıcı arabirimini görüntüler. Web tarayıcısının arabirimine yönelik bir işaretçi DHTML `IWebBrowser2` denetiminde, DHTML nesne modeline erişime izin vermek için kullanılabilir.

ATL Denetim Sihirbazı, hem HTML kaynağında hem de. cpp dosyasında varsayılan kodla bir denetim oluşturur. Denetimi, sihirbaz tarafından oluşturulan olarak derleyip çalıştırabilir ve sonra denetimi Web tarayıcısında veya ActiveX denetimi test kapsayıcısında görüntüleyebilirsiniz. Aşağıdaki resimde, test kapsayıcısında üç düğme görüntülenirken varsayılan ATL DHTML denetimi gösterilmektedir:

![ATL DHTML denetimi](../atl/media/vc52en2.gif "ATL DHTML denetimi")

Bkz. DHTML denetimi oluşturmaya başlamak için [atl dhtml denetimi oluşturma](../atl/creating-an-atl-dhtml-control.md) . Test kapsayıcısına erişme hakkında bilgi için bkz. test [kapsayıcısı Ile özellikleri ve olayları test etme](../mfc/testing-properties-and-events-with-test-container.md) .

## <a name="see-also"></a>Ayrıca bkz.

[DHTML denetimi desteği](../atl/atl-support-for-dhtml-controls.md)
