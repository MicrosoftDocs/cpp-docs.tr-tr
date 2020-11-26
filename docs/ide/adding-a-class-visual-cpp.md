---
title: Sınıf ekleme
ms.date: 05/14/2019
f1_keywords:
- vc.addclass
helpviewer_keywords:
- ATL projects, adding classes
- classes [C++], creating
- classes [C++], adding
- Add Class dialog box
ms.assetid: c34b5f70-4e72-4faa-ba21-e2b05361c4d9
ms.openlocfilehash: b1c64505a63b8720ed7aee855f2bbbbdb9134e28
ms.sourcegitcommit: 6284bca6549e7b4f199d4560c30df6c1278bd4a0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96188841"
---
# <a name="add-a-class"></a>Sınıf ekleme

Visual Studio C++ projesine bir sınıf eklemek için, **Çözüm Gezgini**' de projeye sağ tıklayın, **Ekle**' yi ve ardından **sınıf**' ı seçin. Bu, [Sınıf Ekle iletişim kutusunu](#add-class-dialog-box)açar.

Bir sınıf eklediğinizde, MFC veya ATL 'de zaten var olan sınıflardan farklı bir ad belirtmeniz gerekir. Herhangi bir kitaplıkta zaten bulunan bir ad belirtirseniz, IDE bir hata iletisi gösterir.

Proje adlandırma kuralınızın varolan bir adı kullanmanızı gerektiriyorsa, C++ büyük/küçük harfe duyarlı olduğu için ad içindeki bir veya daha fazla harf durumunu değiştirebilirsiniz. Örneğin, bir sınıfı ad değiştiremeseniz de `CDocument` , adını verebilirsiniz `cdocument` .

## <a name="in-this-section"></a>Bu bölümde

- [Ne tür bir sınıf eklemek istiyorsunuz?](#what-kind-of-class-do-you-want-to-add)
- [Sınıf Ekle iletişim kutusu](#add-class-dialog-box)

## <a name="what-kind-of-class-do-you-want-to-add"></a>Ne tür bir sınıf eklemek istiyorsunuz?

**Sınıf Ekle** iletişim kutusunda, sol bölmedeki **Visual C++** düğümünü genişlettiğinizde, yüklenmiş şablonların çeşitli gruplandırmaları görüntülenir. Gruplar **clr**, **ATL**, **MFC** ve **C++** içerir. Bir grup seçtiğinizde, bu gruptaki kullanılabilir şablonların bir listesi Ortadaki bölmede görüntülenir. Her şablon, bir sınıf için gereken dosyaları ve kaynak kodunu içerir.

Yeni bir sınıf oluşturmak için orta bölmedeki bir şablonu seçin, **ad** kutusuna sınıf için bir ad yazın ve **Ekle**' yi seçin. Bu, sınıf seçeneklerini belirleyebilmeniz için **sınıf ekleme Sihirbazı** ' nı açar.

- MFC sınıfları oluşturma hakkında daha fazla bilgi için bkz. [MFC sınıfı](../mfc/reference/adding-an-mfc-class.md).

- ATL sınıfları oluşturma hakkında daha fazla bilgi için bkz. [ATL Simple Object](../atl/reference/adding-an-atl-simple-object.md).

> [!NOTE]
> **MFC 'ye atl desteği ekleme** şablonu bir sınıf oluşturmaz, bunun yerıne projeyi ATL kullanacak şekilde yapılandırır. Daha fazla bilgi için bkz. [MFC projesinde atl desteği](../mfc/reference/adding-atl-support-to-your-mfc-project.md).

MFC, ATL veya CLR kullanmayan bir C++ sınıfı oluşturmak için, yüklü şablonların **c++** grubundaki **c++ sınıf** şablonunu kullanın. Daha fazla bilgi için bkz. [Genel C++ sınıfı ekleme](../ide/adding-a-generic-cpp-class.md).

İki tür form tabanlı C++ sınıfı vardır. Birinci bir, [CFormView sınıfı](../mfc/reference/cformview-class.md), bir MFC sınıfı oluşturur. İkincisi bir CLR Windows Forms sınıfı oluşturur.

## <a name="add-class-dialog-box"></a>Sınıf Ekle iletişim kutusu

**Sınıf Ekle** iletişim kutusu şunları yapmanıza izin veren şablonlar içerir:

- Varsa, ilgili kod sihirbazını açın. Daha fazla bilgi için bkz. [kod sihirbazları ile Işlevsellik ekleme](../ide/adding-functionality-with-code-wizards-cpp.md).

   \- veya

- Projenize uygun dosya ve kaynak kodu ekleyerek otomatik olarak yeni sınıfınızı oluşturun.

**Proje** menüsünden **Sınıf Ekle** iletişim kutusuna, **Çözüm Gezgini** veya [sınıf görünümü](/visualstudio/ide/viewing-the-structure-of-code)erişebilirsiniz.

> [!NOTE]
> Geçerli projenize uygun olmayan bir sınıf eklemeye çalıştığınızda bir hata iletisi alırsınız. **Sınıf Ekle** iletişim kutusuna dönmek için **Tamam ' ı** seçin.

### <a name="add-class-templates"></a>Sınıf Şablonları Ekle

**Sınıf şablonu Ekle** ' nin dört kategorisi vardır: .net, ATL, MFC ve genel. **Şablonlar** bölmesinde bir şablon seçtiğinizde, seçiminizi açıklayan metin **Kategoriler** ve **Şablonlar** bölmeleri altında görünür.

#### <a name="net"></a>.NET

|Şablon|Ekleme|
|--------------|------------|
|ASP.NET Web hizmeti|Kullanılamaz|
|Bileşen sınıfı (.NET)|Kullanılamaz|
|Yükleyici Sınıfı (.NET)|Kullanılamaz|
|Kullanıcı denetimi (.NET)|Kullanılamaz|
|Windows formu (.NET)|Kullanılamaz|

#### <a name="atl"></a>ATL

|Şablon|Ekleme|
|--------------|------------|
|MFC 'ye ATL desteği ekleme|Kullanılamaz|
|ATL denetimi|[ATL Denetim Sihirbazı](../atl/reference/atl-control-wizard.md)|
|ATL Iletişim kutusu|[ATL iletişim kutusu Sihirbazı](../atl/reference/atl-dialog-wizard.md)|
|ATL basit nesnesi|[ATL basit nesne Sihirbazı](../atl/reference/atl-simple-object-wizard.md)|
|WMI olay sağlayıcısı|WMI olay sağlayıcısı Sihirbazı|
|WMI örnek sağlayıcısı|WMI örnek sağlayıcısı Sihirbazı|

#### <a name="mfc"></a>MFC

|Şablon|Ekleme|
|--------------|------------|
|MFC Sınıfı|[MFC sınıf ekleme Sihirbazı](../mfc/reference/mfc-add-class-wizard.md)|

#### <a name="generic-classes"></a>Genel sınıflar

|Şablon|Ekleme|
|--------------|------------|
|Genel C++ sınıfı|[Genel C++ sınıfı Sihirbazı](./adding-a-generic-cpp-class.md#generic-c-class-wizard)|
