---
description: 'Hakkında daha fazla bilgi edinin: bir nesneye bağlantı noktaları ekleme'
title: Bir nesneye bağlantı noktaları ekleme
ms.date: 11/04/2016
helpviewer_keywords:
- connection points [C++], adding to ATL objects
- Implement Connection Point ATL wizard
ms.assetid: 843531be-4a36-4db0-9d54-e029b1a72a8b
ms.openlocfilehash: 7d8274ab37cef28a58666852aad24db7d945d26e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97166245"
---
# <a name="adding-connection-points-to-an-object"></a>Bir nesneye bağlantı noktaları ekleme

[ATL öğreticisi](../atl/active-template-library-atl-tutorial.md) , bağlantı noktaları desteğiyle, olayların nasıl ekleneceğini ve sonra bağlantı noktasının nasıl uygulanacağını gösteren bir denetim oluşturmayı gösterir. ATL, [ınewctionpointımpl](../atl/reference/iconnectionpointimpl-class.md) sınıfı ile bağlantı noktalarını uygular.

Bir bağlantı noktası uygulamak için iki seçeneğiniz vardır:

- Denetime veya nesneye bir bağlantı noktası ekleyerek kendi giden olay kaynağınızı uygulayın.

- Başka bir tür kitaplığında tanımlanmış bir bağlantı noktası arabirimini yeniden kullanın.

Her iki durumda da, bağlantı noktası uygulama Sihirbazı, işini yapmak için bir tür kitaplığı kullanır.

### <a name="to-add-a-connection-point-to-a-control-or-object"></a>Bir denetime veya nesneye bağlantı noktası eklemek için

1. . IDL dosyasının kitaplık bloğunda bir dispınterface tanımlayın. ATL Denetim Sihirbazı ile denetimi oluştururken bağlantı noktaları desteğini etkinleştirdiyseniz, dispınterface zaten oluşturulur. Denetimi oluştururken bağlantı noktaları desteğini etkinleştirmezseniz,. IDL dosyasına el ile bir dispınterface eklemeniz gerekir. Aşağıda, bir dispınterface örneği verilmiştir. Giden arabirimlerin arabirim gönderimi gerekmez, ancak VBScript ve JScript gibi birçok komut dosyası dili bunu gerektirir, bu nedenle bu örnek iki dispınterfaces kullanır:

   [!code-cpp[NVC_ATL_Windowing#81](../atl/codesnippet/cpp/adding-connection-points-to-an-object_1.idl)]

   Bir GUID oluşturmak için uuidgen.exe ya da guidgen.exe yardımcı programını kullanın.

2. `[default,source]`Proje. IDL dosyasındaki nesnenin coclass 'ından arabirim olarak dispınterface 'i ekleyin. Daha sonra, denetimi oluştururken bağlantı noktaları desteğini etkinleştirdiyseniz, ATL Denetim Sihirbazı `[default,source` ] girdisini oluşturacaktır. Bu girişi el ile eklemek için satırı kalın olarak ekleyin:

   [!code-cpp[NVC_ATL_Windowing#82](../atl/codesnippet/cpp/adding-connection-points-to-an-object_2.idl)]

   Örnek için, [Circ](../overview/visual-cpp-samples.md) ATL örneğindeki. IDL dosyasına bakın.

3. Olay arabirimine Yöntemler ve özellikler eklemek için Sınıf Görünümü kullanın. Sınıf Görünümü sınıfa sağ tıklayın, kısayol menüsünde **Ekle** ' nin üzerine gelin ve **bağlantı noktası Ekle**' ye tıklayın.

4. Bağlantı noktası uygulama Sihirbazı 'nın **kaynak arabirimleri** liste kutusunda, **projenin arabirimlerini** seçin. Denetiminiz için bir arabirim seçer ve **Tamam**' a basarsanız, şunları yapmanız gerekir:

   - Olay için giden çağrıları oluşturacak kodu uygulayan bir olay proxy sınıfı ile bir üst bilgi dosyası oluşturun.

   - Bağlantı noktası eşlemesine bir giriş ekleyin.

   Ayrıca bilgisayarınızdaki tüm tür kitaplıklarının listesini görürsünüz. Başka bir tür kitaplığında bulunan tam aynı giden arabirimi uygulamak istiyorsanız bağlantı noktanızı tanımlamak için bu diğer tür kitaplıklarından yalnızca birini kullanmalısınız.

### <a name="to-reuse-a-connection-point-interface-defined-in-another-type-library"></a>Başka bir tür kitaplığında tanımlanan bir bağlantı noktası arabirimini yeniden kullanmak için

1. Sınıf Görünümü, bir **BEGIN_COM_MAP** makrosunu uygulayan bir sınıfa sağ tıklayın, kısayol menüsünde **Ekle** ' nin üzerine gelin ve **bağlantı noktası Ekle**' ye tıklayın.

2. Bağlantı noktası uygulama Sihirbazı 'nda, tür kitaplığı 'nda bir tür kitaplığı ve arabirim seçin ve **Ekle**' ye tıklayın.

3. . IDL dosyasını şu şekilde düzenleyin:

   - Olay kaynağı kullanılan nesnenin. IDL dosyasındaki dispınterface 'i kopyalayın.

   - Bu tür kitaplığı üzerinde **ımportlib** yönergesini kullanın.

## <a name="see-also"></a>Ayrıca bkz.

[Bağlantı noktası](../atl/atl-connection-points.md)
