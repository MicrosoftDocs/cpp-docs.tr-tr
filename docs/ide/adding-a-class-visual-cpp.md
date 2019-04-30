---
title: Bir sınıf ekleyin
ms.date: 11/08/2018
f1_keywords:
- vc.codewiz.classes.adding
- vc.addclass
helpviewer_keywords:
- ATL projects, adding classes
- classes [C++], creating
- classes [C++], adding
- Add Class dialog box
ms.assetid: c34b5f70-4e72-4faa-ba21-e2b05361c4d9
ms.openlocfilehash: 21dd4b1936eda201df8283146ba9f41fa81e11de
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62375892"
---
# <a name="add-a-class"></a>Bir sınıf ekleyin

Visual C++ projesinde bir sınıf eklemek için **Çözüm Gezgini**, projeye sağ tıklayın, seçin **Ekle**ve ardından **sınıfı**. Bu açılır [Sınıf Ekle iletişim kutusu](#add-class-dialog-box).

Bir sınıf eklediğinizde, MFC veya ATL içinde zaten mevcut sınıflardan farklı bir ad belirtmelisiniz Her iki Kitaplığı'nda zaten bir ad belirtirseniz, IDE bir hata iletisi gösterir.

Adlandırma projeniz var olan bir adı kullanmak gerektiriyorsa, C++ büyük/küçük harfe duyarlıdır çünkü daha sonra yalnızca büyük/küçük harf, bir veya daha fazla ad değiştirebilirsiniz. Örneğin, bir sınıf adı olamaz ancak `CDocument`, ad verebilirsiniz `cdocument`.

## <a name="in-this-section"></a>Bu bölümde

- [Ne tür bir sınıf eklemek istiyor musunuz?](#what-kind-of-class-do-you-want-to-add)
- [Sınıf Ekle iletişim kutusu](#add-class-dialog-box)

## <a name="what-kind-of-class-do-you-want-to-add"></a>Ne tür bir sınıf eklemek istiyor musunuz?

İçinde **sınıfı Ekle** genişlettikten iletişim kutusu, **Visual C++** düğümü sol bölmedeki yüklü şablonlar birkaç gruplandırmaları görüntülenir. Grupları dahil **CLR**, **ATL**, **MFC**, ve **C++**. Bir grubu seçtiğinizde, o grup içindeki kullanılabilir şablonların listesini Orta bölmede görüntülenir. Her şablon, bir sınıf için gerekli olan kaynak kodu ve dosyaları içerir.

Yeni bir sınıf oluşturmak için Orta bölmede bir şablon seçin, sınıf için bir ad yazın **adı** kutusunda ve seçin **Ekle**. Bu açılır **sınıf Ekleme Sihirbazı'nı** sınıfı için seçenekleri belirtebilirsiniz.

- MFC sınıfları oluşturma hakkında daha fazla bilgi için bkz. [MFC sınıfı](../mfc/reference/adding-an-mfc-class.md).

- ATL sınıfları oluşturma hakkında daha fazla bilgi için bkz. [ATL Basit Nesne](../atl/reference/adding-an-atl-simple-object.md).

> [!NOTE]
> Şablon **MFC ATL desteği Ekle** bir sınıf oluşturmaz, ancak bunun yerine projeyi ATL kullanacak şekilde yapılandırır Daha fazla bilgi için [bir MFC projesinde ATL desteği](../mfc/reference/adding-atl-support-to-your-mfc-project.md).

MFC, ATL veya CLR kullanmayan C++ sınıfı yapma **C++ sınıfı** şablonunda **C++** Grup yüklü şablonlar. Daha fazla bilgi için [genel C++ sınıfı ekleme](../ide/adding-a-generic-cpp-class.md).

İki tür form tabanlı C++ sınıfları kullanılabilir. Birinci [CFormView sınıfı](../mfc/reference/cformview-class.md), MFC sınıfı oluşturur. İkinci bir CLR Windows Forms sınıf oluşturur.

## <a name="add-class-dialog-box"></a>Sınıf Ekle iletişim kutusu

**Sınıfı Ekle** iletişim kutusu olanak tanıyan şablonları içerir:

- Varsa, karşılık gelen bir kod Sihirbazı açın. Daha fazla bilgi için [kod sihirbazlarıyla işlevsellik ekleme](../ide/adding-functionality-with-code-wizards-cpp.md).

   \- veya -

- Kaynak kodu ve uygun dosyaları projenize ekleyerek otomatik olarak, yeni bir sınıf oluşturun.

Erişebildiğiniz **sınıfı Ekle** iletişim kutusundan **proje** menüsünde **Çözüm Gezgini**, veya [sınıf görünümü](/visualstudio/ide/viewing-the-structure-of-code).

> [!NOTE]
> Geçerli projeniz için uygun olmayan bir sınıf eklemeye çalıştığınızda, bir hata iletisi alırsınız. Seçin **Tamam** dönmek için **sınıfı Ekle** iletişim kutusu.

### <a name="add-class-templates"></a>Sınıf şablonları ekleme

Dört kategorisi vardır **sınıfı Ekle** şablonları: .NET, ATL, MFC ve genel. Bir şablonda seçtiğinizde **şablonları** bölmesinde yaptığınız seçime açıklayan metin altında görünür **kategorileri** ve **şablonları** bölmeleri.

#### <a name="net"></a>.NET

|Şablon|Sihirbazı|
|--------------|------------|
|ASP.NET Web hizmeti|Yok|
|Bileşen sınıfı (.NET)|Yok|
|Yükleyici sınıfı (.NET)|Yok|
|Kullanıcı denetimi (.NET)|Yok|
|Windows Form (.NET)|Yok|

#### <a name="atl"></a>ATL

|Şablon|Sihirbazı|
|--------------|------------|
|MFC'ye ATL desteği Ekle|Yok|
|ATL Active Server Page bileşeni|[ATL active server sayfa bileşeni Sihirbazı](../atl/reference/atl-active-server-page-component-wizard.md)|
|ATL denetimi|[ATL Denetim Sihirbazı](../atl/reference/atl-control-wizard.md)|
|ATL iletişim kutusu|[ATL iletişim kutusu Sihirbazı](../atl/reference/atl-dialog-wizard.md)|
|ATL COM + 1.0 bileşeni|[ATL COM + 1.0 bileşeni Sihirbazı](../atl/reference/atl-com-plus-1-0-component-wizard.md)|
|ATL OLEDB tüketicisi|[ATL OLE DB Tüketicisi Sihirbazı](../atl/reference/atl-ole-db-consumer-wizard.md)|
|ATL OLEDB Sağlayıcısı|[ATL OLE DB sağlayıcısı Sihirbazı](../atl/reference/atl-ole-db-provider-wizard.md)|
|ATL özellik sayfası|[ATL Özellik Sayfası Sihirbazı](../atl/reference/atl-property-page-wizard.md)|
|ATL Basit Nesne|[ATL Basit Nesne Sihirbazı](../atl/reference/atl-simple-object-wizard.md)|
|WMI Olay sağlayıcısı|WMI Olay sağlayıcısı Sihirbazı|
|WMI örnek sağlayıcısı|WMI örnek sağlayıcısı Sihirbazı|

#### <a name="mfc"></a>MFC

|Şablon|Sihirbazı|
|--------------|------------|
|MFC Sınıfı|[MFC sınıf Ekleme Sihirbazı](../mfc/reference/mfc-add-class-wizard.md)|
|ActiveX denetiminden MFC sınıfı|[ActiveX denetimi sihirbazından sınıf ekleme](../ide/add-class-from-activex-control-wizard.md)|
|Typelib'den MFC sınıfı|[Typelib sihirbazından sınıf ekleme](../mfc/reference/add-class-from-typelib-wizard.md)|
|MFC ODBC Tüketicisi|[MFC ODBC Tüketicisi Sihirbazı](../mfc/reference/mfc-odbc-consumer-wizard.md)|

#### <a name="generic-classes"></a>Genel sınıflar

|Şablon|Sihirbazı|
|--------------|------------|
|Genel C++ sınıfı|[Genel C++ sınıfı Sihirbazı](../ide/generic-cpp-class-wizard.md)|
