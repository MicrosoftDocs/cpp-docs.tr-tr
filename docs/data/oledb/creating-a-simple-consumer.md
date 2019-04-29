---
title: Basit Tüketici Oluşturma
ms.date: 11/06/2018
helpviewer_keywords:
- OLE DB consumers, creating
ms.assetid: ae32d657-72ea-4db8-9839-75cb5cff68ae
ms.openlocfilehash: 060a39a8436ff73900ebfaea7d1c882b9862ee7e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62362031"
---
# <a name="creating-a-simple-consumer"></a>Basit Tüketici Oluşturma

Kullanım **ATL projesi Sihirbazı** ve **ATL OLE DB Tüketicisi Sihirbazı** bir OLE DB Şablonları tüketicisi oluşturmak için.

## <a name="to-create-a-console-application-for-an-ole-db-consumer"></a>Bir konsol uygulaması için bir OLE DB Tüketicisi Oluşturma

1. Üzerinde **dosya** menüsünde tıklatın **yeni**ve ardından **proje**.

   **Yeni Proje** iletişim kutusu görünür.

1. İçinde **proje türleri** bölmesinde tıklayın **yüklü** > **Visual C++** > **Windows Masaüstü** klasörü ve ardından **Windows Masaüstü Sihirbazı'nı** simgesini **şablonları** bölmesi. İçinde **adı** kutusunda, projenizin adını girin, örneğin, *MyCons*.

1. **Tamam**'ı tıklatın.

   **Windows Masaüstü projesi** Sihirbazı görünür.

1. Üzerinde **uygulama ayarları** sayfasında **konsol uygulaması**ve ardından **gibi ortak başlık dosyaları eklemek için ATL**.

1. Tıklayın **Tamam** sihirbazı kapatın ve projeyi oluşturmak için.

Ardından, **ATL OLE DB Tüketicisi Sihirbazı** OLE DB Tüketici nesne eklemek için.

## <a name="to-create-a-consumer-with-the-atl-ole-db-consumer-wizard"></a>ATL OLE DB Tüketicisi Sihirbazı ile bir tüketici oluşturma

1. İçinde **Çözüm Gezgini**, sağ `MyCons` proje.

1. Kısayol menüsünde **Ekle**ve ardından **yeni öğe**.

   **Yeni Öğe Ekle** iletişim kutusu görünür.

1. İçinde **kategorileri** bölmesinde tıklayın **yüklü** > **Visual C++** > **ATL**, tıklayın**ATL OLEDB tüketicisi** simgesini **şablonları** bölmesi ve ardından **Ekle**.

   **ATL OLEDB tüketicisi Sihirbazı** görünür.

1. Tıklayın **veri kaynağı** düğmesi.

   **Veri bağlantı özellikleri** iletişim kutusu görüntülenir.

1. İçinde **veri bağlantı özellikleri** iletişim kutusunda, aşağıdakileri yapın:

   1. Üzerinde **sağlayıcısı** sekmesinde, bir OLE DB sağlayıcısı belirtin.

   1. Üzerinde **bağlantı** sekmesinde, sunucu üzerinde sunucu adı, oturum açma kimliği ve parolası veri kaynağı ve veritabanı gibi gerekli bilgileri belirtin.

      > [!NOTE]
      > Bir güvenlik sorun **parola kaydetmeye izin ver** özelliği **veri bağlantı özellikleri** iletişim kutusu. İçinde **sunucuya oturum açmak için bilgi girin**, iki radyo düğmeleri vardır: **Kullanım Windows NT tümleşik güvenliği** ve **belirli bir kullanıcı adı ve parolayı kullanın**.

      > [!NOTE]
      > Seçerseniz **belirli bir kullanıcı adı ve parolayı kullanın**, parola kaydetme seçeneğiniz vardır (kullanarak **parola kaydetmeye izin ver** onay kutusu); ancak, bu seçeneği güvenli değildir. Seçtiğiniz önerilir **kullanım Windows NT tümleşik güvenliği**; bu seçenek, kimliğinizi doğrulamak için Windows NT kullanır.

      > [!NOTE]
      > Windows NT tümleşik güvenliği kullanamaz, kullanıcıdan parola veya parola korumak amacıyla güvenlik mekanizmaları ile bir konumda depolamak için bir orta katman uygulama kullanmalıdır (yerine kaynak kodunda).

   1. Sağlayıcınız ve diğer ayarları seçtikten sonra **Test Bağlantısı** önceki iletişim kutusu sayfalarında yapılan seçimleri doğrulayın. Varsa **sonuçları** kutusuna raporları `Test connection succeeded`, tıklayın **Tamam** veri bağlantısı oluşturmak için.

   **Veritabanı nesnesini Seç** iletişim kutusu görüntülenir.

1. Ağaç denetimi tablosu, görünümü veya saklı yordam seçmek için kullanın. Bu örnekte, seçin `Products` tablosunda `Northwind` veritabanı.

1. **Tamam**'ı tıklatın. Bu size döndürür **ATL OLE DB Tüketicisi Sihirbazı**.

1. Sihirbaz adlarını tamamlandıktan `Class` ve **.h dosyası** görünümü, tablonun adını temel alarak veya saklı yordamı, seçtiğiniz. İsterseniz, bu adlar düzenleyebilirsiniz.

1. NET **öznitelikli** Sihirbazı'nı kullanarak tüketici kod oluşturur, böylece onay kutusunu [OLE DB şablon sınıfları](../../data/oledb/ole-db-consumer-templates-reference.md) varsayılan yerine [OLE DB tüketici öznitelikleri](../../windows/ole-db-consumer-attributes.md).

1. Altında **türü**seçin **komut**.

   Sihirbazın oluşturduğu bir [CCommand](../../data/oledb/ccommand-class.md)-seçerseniz tüketici tabanlı **komut** veya [CTable](../../data/oledb/ctable-class.md)-seçerseniz tüketici tabanlı **tablo**. Nesneyi seçtikten sonra adlı tablo veya komut sınıfı, ancak adını düzenleyebilirsiniz.

1. Altında **Destek**, bırakın **değişiklik**, **Ekle**, ve **Sil** kutularının.

   Seçin **değişiklik**, **Ekle**, ve **Sil** değiştirme, ekleme ve satır kümesindeki kayıtları silme desteklemek için onay kutularını. Depolayabilir ve bu verileri veri yazma hakkında daha fazla bilgi için bkz: [satır kümelerini güncelleştirme](../../data/oledb/updating-rowsets.md).

1. Tıklayın **son** tüketici oluşturmak için.

Sihirbaz gösterildiği gibi bir komut ve bir kullanıcı kaydı sınıfı oluşturur [kodla](../../data/oledb/consumer-wizard-generated-classes.md). Komut sınıfının girdiğiniz ad olacaktır `Class` sihirbazda kutusuna (Bu durumda, `CProducts`), ve kullanıcı kayıt sınıfı bir adı olacaktır "*ClassName*erişimci" (Bu durumda, `CProductsAccessor`).

> [!NOTE]
> Sihirbaz aşağıdaki satır içine yerleştirir `Products.h`:

```cpp
#error Security Issue: The connection string may contain a password
```

> [!NOTE]
> Bu satırı önleyen tüketici uygulama engeller ve bağlantı dizenizi sabit kodlanmış parolalar için denetlenecek anımsatır. Bağlantı dizenizi denetledikten sonra bu kod satırı kaldırabilirsiniz.

## <a name="see-also"></a>Ayrıca bkz.

[Sihirbaz Kullanarak bir OLE DB Tüketicisi Oluşturma](../../data/oledb/creating-an-ole-db-consumer-using-a-wizard.md)
