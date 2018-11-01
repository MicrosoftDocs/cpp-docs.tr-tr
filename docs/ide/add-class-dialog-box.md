---
title: Sınıf Ekle İletişim Kutusu
ms.date: 11/04/2016
f1_keywords:
- vc.addclass
helpviewer_keywords:
- Add Class dialog box
ms.assetid: 916259b8-8e5f-4267-bd10-313483beba67
ms.openlocfilehash: 405f88f7f77ea75584ec3cfd76af1ea9a0457ed6
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50643202"
---
# <a name="add-class-dialog-box"></a>Sınıf Ekle İletişim Kutusu

**Sınıfı Ekle** iletişim kutusu olanak tanıyan şablonları içerir:

- Varsa, karşılık gelen bir kod Sihirbazı açın. Daha fazla bilgi için [kod sihirbazlarıyla işlevsellik ekleme](../ide/adding-functionality-with-code-wizards-cpp.md).

   \- veya -

- Kaynak kodu ve uygun dosyaları projenize ekleyerek otomatik olarak, yeni bir sınıf oluşturun.

Erişebildiğiniz **sınıfı Ekle** iletişim kutusundan **proje** menüsünde **Çözüm Gezgini**, veya [sınıf görünümü](/visualstudio/ide/viewing-the-structure-of-code).

> [!NOTE]
>  Geçerli projeniz için uygun olmayan bir sınıf eklemeye çalıştığınızda, bir hata iletisi alırsınız. Tıklayın **Tamam** dönmek için **sınıfı Ekle** iletişim kutusu.

## <a name="add-class-templates"></a>Sınıf şablonları ekleme

Dört kategorisi vardır **sınıfı Ekle** şablonları: .NET, ATL, MFC ve genel. Bir şablonda seçtiğinizde **şablonları** bölmesinde yaptığınız seçime açıklayan metin altında görünür **kategorileri** ve **şablonları** bölmeleri.

### <a name="net"></a>.NET

|Şablon|Sihirbazı|
|--------------|------------|
|ASP.NET Web hizmeti|Yok|
|Bileşen sınıfı (.NET)|Yok|
|Yükleyici sınıfı (.NET)|Yok|
|Kullanıcı denetimi (.NET)|Yok|
|Windows Form (.NET)|Yok|

### <a name="atl"></a>ATL

|Şablon|Sihirbazı|
|--------------|------------|
|MFC'ye ATL desteği Ekle|Yok|
|ATL Active Server Page bileşeni|[ATL Active Server Page Bileşeni Sihirbazı](../atl/reference/atl-active-server-page-component-wizard.md)|
|ATL denetimi|[ATL Denetimi Sihirbazı](../atl/reference/atl-control-wizard.md)|
|ATL iletişim kutusu|[ATL İletişim Kutusu Sihirbazı](../atl/reference/atl-dialog-wizard.md)|
|ATL COM + 1.0 bileşeni|[ATL COM+ 1.0 Bileşeni Sihirbazı](../atl/reference/atl-com-plus-1-0-component-wizard.md)|
|ATL OLEDB tüketicisi|[ATL OLE DB Tüketicisi Sihirbazı](../atl/reference/atl-ole-db-consumer-wizard.md)|
|ATL OLEDB Sağlayıcısı|[ATL OLE DB Sağlayıcısı Sihirbazı](../atl/reference/atl-ole-db-provider-wizard.md)|
|ATL özellik sayfası|[ATL Özellik Sayfası Sihirbazı](../atl/reference/atl-property-page-wizard.md)|
|ATL Basit Nesne|[ATL Basit Nesne Sihirbazı](../atl/reference/atl-simple-object-wizard.md)|
|WMI Olay sağlayıcısı|WMI Olay sağlayıcısı Sihirbazı|
|WMI örnek sağlayıcısı|WMI örnek sağlayıcısı Sihirbazı|

### <a name="mfc"></a>MFC

|Şablon|Sihirbazı|
|--------------|------------|
|MFC Sınıfı|[MFC Sınıf Ekleme Sihirbazı](../mfc/reference/mfc-add-class-wizard.md)|
|ActiveX denetiminden MFC sınıfı|[ActiveX Denetimi Sihirbazından Sınıf Ekleme](../ide/add-class-from-activex-control-wizard.md)|
|Typelib'den MFC sınıfı|[Typelib sihirbazından sınıf ekleme](../mfc/reference/add-class-from-typelib-wizard.md)|
|MFC ODBC Tüketicisi|[MFC ODBC Tüketici Sihirbazı](../mfc/reference/mfc-odbc-consumer-wizard.md)|

### <a name="generic-classes"></a>Genel Sınıflar

|Şablon|Sihirbazı|
|--------------|------------|
|Genel C++ sınıfı|[Genel C++ Sınıfı Sihirbazı](../ide/generic-cpp-class-wizard.md)|

## <a name="see-also"></a>Ayrıca Bkz.

[Üye işlevi ekleme](../ide/adding-a-member-function-visual-cpp.md)<br>
[Üye değişkeni ekleme](../ide/adding-a-member-variable-visual-cpp.md)<br>
[Bir sanal işlevi geçersiz kılma](../ide/overriding-a-virtual-function-visual-cpp.md)<br>
[MFC ileti işleyicisi](../mfc/reference/adding-an-mfc-message-handler.md)<br>
[Sınıf yapısında gezinme](../ide/navigating-the-class-structure-visual-cpp.md)