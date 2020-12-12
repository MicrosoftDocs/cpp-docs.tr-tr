---
description: 'Daha fazla bilgi edinin: basit bir tüketici oluşturma'
title: Basit Tüketici Oluşturma
ms.date: 05/09/2019
helpviewer_keywords:
- OLE DB consumers, creating
ms.assetid: ae32d657-72ea-4db8-9839-75cb5cff68ae
ms.openlocfilehash: 338f5b13581188a9eb8a43d42c3074cb9788202a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97323239"
---
# <a name="creating-a-simple-consumer"></a>Basit Tüketici Oluşturma

::: moniker range="msvc-160"

ATL OLE DB Tüketici Sihirbazı, Visual Studio 2019 ve sonrasında kullanılamaz. İşlevselliği el ile de ekleyebilirsiniz. Daha fazla bilgi için bkz. [Sihirbaz kullanmadan tüketici oluşturma](creating-a-consumer-without-using-a-wizard.md).

::: moniker-end

::: moniker range="<=msvc-150"

Bir OLE DB Şablonları tüketicisi oluşturmak için **atl Proje Sihirbazı** ve **ATL OLE DB Tüketici Sihirbazı** ' nı kullanın.

## <a name="to-create-a-console-application-for-an-ole-db-consumer"></a>OLE DB tüketicisi için bir konsol uygulaması oluşturmak için

1. **Dosya** menüsünde **Yeni** ve **Proje**’ye sırasıyla tıklayın.

   **Yeni Proje** iletişim kutusu görünür.

1. **Proje türleri** bölmesinde,   >    >  **Windows Masaüstü** Visual C++ yüklendi klasörüne tıklayın ve ardından **Şablonlar** bölmesinde **Windows Masaüstü Sihirbazı** simgesine tıklayın. **Ad** kutusuna projenizin adını (örneğin, *MyCons*) girin.

1. **Tamam** düğmesine tıklayın.

   **Windows Masaüstü projesi** Sihirbazı görüntülenir.

1. **Uygulama ayarları** sayfasında **konsol uygulaması**' nı seçin ve ardından **ATL Için ortak üst bilgi dosyaları Ekle**' yi seçin.

1. Sihirbazı kapatmak ve projeyi oluşturmak için **Tamam** ' ı tıklatın.

Sonra, bir OLE DB tüketici nesnesi eklemek için **ATL OLE DB Tüketici Sihirbazı** ' nı kullanın.

## <a name="to-create-a-consumer-with-the-atl-ole-db-consumer-wizard"></a>ATL OLE DB tüketici sihirbazıyla bir tüketici oluşturmak için

1. **Çözüm Gezgini**, projeye sağ tıklayın `MyCons` .

1. Kısayol menüsünde, **Ekle**' ye ve ardından **Yeni öğe**' ye tıklayın.

   **Yeni Öğe Ekle** iletişim kutusu görünür.

1. **Kategoriler** bölmesinde, ATL Visual C++ **yüklendi** ' ye tıklayın >  > , **Şablonlar** bölmesinde **ATL OLEDB tüketicisi** simgesine tıklayın ve ardından **Ekle**' ye tıklayın.

   **ATL OLEDB tüketicisi Sihirbazı** görüntülenir.

1. **Veri kaynağı** düğmesine tıklayın.

   **Veri bağlantısı özellikleri** iletişim kutusu görüntülenir.

1. **Veri bağlantısı özellikleri** iletişim kutusunda, şunları yapın:

   1. **Sağlayıcı** sekmesinde bir OLE DB sağlayıcısı belirtin.

   1. **Bağlantı** sekmesinde, sunucuda veri kaynağınız ve veritabanınız için sunucu adı, oturum açma kimliği ve parola gibi gerekli bilgileri belirtin.

      > [!NOTE]
      > **Veri bağlantısı özellikleri** iletişim kutusunun **Parola kaydetmeye izin ver** özelliğinin bulunduğu bir güvenlik sorunu vardır. **Sunucuda oturum açmak için bilgi girin**' de iki radyo düğmesi vardır: **Windows NT tümleşik güvenlik kullanın** ve **belirli bir Kullanıcı adı ve parola kullanın**.

      > [!NOTE]
      > **Belirli bir Kullanıcı adı ve parola kullan**' ı seçerseniz, parolayı kaydetme seçeneğiniz vardır ( **Parola kaydetmeye izin ver** onay kutusunu kullanarak); Ancak, bu seçenek güvenli değildir. **WINDOWS NT tümleşik güvenliği kullan**' ı seçmeniz önerilir. Bu seçenek, kimliğinizi doğrulamak için Windows NT kullanır.

      > [!NOTE]
      > Windows NT tümleşik güvenlik 'i kullanmıyorsanız, kullanıcıdan parola istemek veya parolayı korumaya yardımcı olması için güvenlik mekanizmalarına sahip bir konumda depolamak için bir orta katmanlı uygulama kullanmanız gerekir (kaynak kodu yerine).

   1. Sağlayıcınızı ve diğer ayarları seçtikten sonra, önceki iletişim kutusu sayfalarında yapılan seçimleri doğrulamak için **Bağlantıyı Sına** ' ya tıklayın. **Sonuçlar** kutusu bildirirse `Test connection succeeded` , veri bağlantısını oluşturmak için **Tamam** ' ı tıklatın.

   **Veritabanı nesnesi Seç** iletişim kutusu görünür.

1. Ağaç denetimini kullanarak bir tablo, görünüm veya saklı yordam seçin. Bu örnekte, `Products` veritabanından tabloyu seçin `Northwind` .

1. **Tamam** düğmesine tıklayın. Bu, sizi **ATL OLE DB Tüketici Sihirbazı**'na döndürür.

1. Sihirbaz, `Class` Seçtiğiniz tablo, görünüm veya saklı yordamın adına göre ve **. h dosyası** adlarını tamamlar. İsterseniz bu adları düzenleyebilirsiniz.

1. Sihirbazın, varsayılan [OLE DB tüketici öznitelikleri](../../windows/attributes/ole-db-consumer-attributes.md)yerine [OLE DB şablon sınıfları](../../data/oledb/ole-db-consumer-templates-reference.md) kullanarak tüketici kodu oluşturması için **öznitelikli** onay kutusunu temizleyin.

1. **Tür** altında **komut**' yi seçin.

   Sihirbaz, **tablo**' yı seçerseniz, **Command** veya [CTable](../../data/oledb/ctable-class.md)tabanlı bir tüketici seçerseniz, bir [CCommand](../../data/oledb/ccommand-class.md)tabanlı tüketici oluşturur. Tablo veya komut sınıfı Seçili nesneden sonra adlandırılır, ancak adı düzenleyebilirsiniz.

1. **Destek** altında **değişiklik**, **ekleme** ve **silme** kutularını işaretsiz bırakın.

   Satır kümesindeki kayıtları değiştirme, ekleme ve silmeyi desteklemek için **Değiştir**, **Ekle** ve **Sil** onay kutularını seçin. Veri deposuna veri yazma hakkında daha fazla bilgi için bkz. [satır kümelerini güncelleştirme](../../data/oledb/updating-rowsets.md).

1. Tüketicisi oluşturmak için **son** ' a tıklayın.

Sihirbaz, [tüketici Wizard-Generated sınıflarında](../../data/oledb/consumer-wizard-generated-classes.md)gösterildiği gibi bir komut sınıfı ve bir kullanıcı kayıt sınıfı oluşturur. Komut sınıfı, sihirbazdaki kutuya girdiğiniz ada sahip olacaktır `Class` (Bu durumda, `CProducts` ) ve Kullanıcı kayıt sınıfı "*ClassName* erişimcisi" (Bu örnekte,) biçiminde bir ada sahip olacaktır `CProductsAccessor` .

> [!NOTE]
> Sihirbaz aşağıdaki satırı içine koyar `Products.h` :

```cpp
#error Security Issue: The connection string may contain a password
```

> [!NOTE]
> Bu satır, tüketici uygulamasının derlenmesini önler ve Bağlantı dizenizi sabit kodlanmış parolalara göre denetlemeye hatırlatır. Bağlantı dizenizi denetledikten sonra bu kod satırını kaldırabilirsiniz.

::: moniker-end

## <a name="see-also"></a>Ayrıca bkz.

[Sihirbaz kullanarak OLE DB tüketicisi oluşturma](../../data/oledb/creating-an-ole-db-consumer-using-a-wizard.md)
