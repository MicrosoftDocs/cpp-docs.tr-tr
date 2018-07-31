---
title: Basit Tüketici oluşturma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- OLE DB consumers, creating
ms.assetid: ae32d657-72ea-4db8-9839-75cb5cff68ae
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: e9f7c5a51765e2ce29df503aeefa9f850b71b1d4
ms.sourcegitcommit: 889a75be1232817150be1e0e8d4d7f48f5993af2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/30/2018
ms.locfileid: "39339860"
---
# <a name="creating-a-simple-consumer"></a>Basit Tüketici Oluşturma
ATL OLE DB Tüketicisi Sihirbazı ve ATL projesi Sihirbazı bir OLE DB Şablonları tüketicisi oluşturmak için kullanın.  
  
### <a name="to-create-a-console-application-for-an-ole-db-consumer"></a>Bir konsol uygulaması için bir OLE DB Tüketicisi Oluşturma  
  
1.  Üzerinde **dosya** menüsünde tıklatın **yeni**ve ardından **proje**.  
  
     **Yeni proje** iletişim kutusu görüntülenir.  
  
2.  Proje Türleri bölmesinde **Visual C++ projeleri** klasörünü ve ardından **Win32 projesi** Şablonlar bölmesinde simgesi. İçinde **adı** kutusunda, projenizin adını girin, örneğin, **MyCons**.  
  
3.  **Tamam**'ı tıklatın.  
  
     Win32 Proje Sihirbazı görünür.  
  
4.  Üzerinde **uygulama ayarları** sayfasında **konsol uygulaması**ve ardından **ATL için destek ekleme**.  
  
5.  Tıklayın **son** sihirbazı kapatın ve projeyi oluşturmak için.  
  
 Ardından, OLE DB Tüketici nesne eklemek için ATL OLE DB Tüketicisi Sihirbazı kullanın.  
  
#### <a name="to-create-a-consumer-with-the-atl-ole-db-consumer-wizard"></a>ATL OLE DB Tüketicisi Sihirbazı ile bir tüketici oluşturma  
  
1.  Sınıf Görünümü'nde sağ `MyCons` proje.  
  
2.  Kısayol menüsünde **Ekle**ve ardından **sınıfı Ekle**.  
  
     **Sınıfı Ekle** iletişim kutusu görüntülenir.  
  
3.  Kategorileri bölmesinden **Visual C++**, tıklayın **ATL OLE DB Tüketicisi** Şablonlar bölmesinde ve ardından simge **açık**.  
  
     ATL OLE DB Tüketicisi Sihirbazı görünür.  
  
4.  Tıklayın **veri kaynağı** düğmesi.  
  
     **Veri bağlantı özellikleri** iletişim kutusu görüntülenir.  
  
5.  İçinde **veri bağlantı özellikleri** iletişim kutusunda, aşağıdakileri yapın:  
  
    -   Üzerinde **sağlayıcısı** sekmesinde, bir OLE DB sağlayıcısı belirtin.  
  
    -   Üzerinde **bağlantı** sekmesinde, sunucu üzerinde sunucu adı, oturum açma kimliği ve veritabanı ve veri kaynağı için parola belirtin.  
  
    > [!NOTE]
    >  Bir güvenlik sorun **parola kaydetmeye izin ver** özelliği **veri bağlantı özellikleri** iletişim kutusu. İçinde **sunucuya oturum açmak için bilgi girin**, iki radyo düğmeleri vardır: **kullanım Windows NT tümleşik güvenliği** ve **belirli bir kullanıcı adı ve parolayı kullanın**.  
  
    > [!NOTE]
    >  Seçerseniz **belirli bir kullanıcı adı ve parolayı kullanın**, parola kaydetme seçeneğiniz vardır (kullanarak **parola kaydetmeye izin ver** onay kutusu); ancak, bu seçeneği güvenli değildir. Seçtiğiniz önerilir **kullanım Windows NT tümleşik güvenliği**; bu seçenek, kimliğinizi doğrulamak için Windows NT kullanır.  
  
    > [!NOTE]
    >  Windows NT tümleşik güvenliği kullanamaz, kullanıcıdan parola veya parola korumak amacıyla güvenlik mekanizmaları ile bir konumda depolamak için bir orta katman uygulama kullanmalıdır (yerine kaynak kodunda).  
  
     Sağlayıcınız ve diğer ayarları seçtikten sonra **Test Bağlantısı** önceki iletişim kutusu sayfalarında yapılan seçimleri doğrulayın. Varsa **sonuçları** kutusuna raporları `Test connection succeeded`, tıklayın **Tamam** veri bağlantısı oluşturmak için.  
  
     **Veritabanı nesnesini Seç** iletişim kutusu görüntülenir.  
  
6.  Ağaç denetimi tablosu, görünümü veya saklı yordam seçmek için kullanın. Bu yordam amacıyla, Northwind veritabanından Ürünler tablosu seçin.  
  
7.  **Tamam**'ı tıklatın. ATL OLE DB Tüketicisi Sihirbazı için döndürür.  
  
8.  Sihirbaz adlarını tamamlandıktan `Class` ve **.h dosyası** görünümü, tablonun adını temel alarak veya saklı yordamı, seçtiğiniz. İsterseniz, bu adlar düzenleyebilirsiniz.  
  
9. NET **öznitelikli** Sihirbazı'nı kullanarak tüketici kod oluşturur, böylece onay kutusunu [OLE DB şablon sınıfları](../../data/oledb/ole-db-consumer-templates-reference.md) varsayılan yerine [OLE DB tüketici öznitelikleri](../../windows/ole-db-consumer-attributes.md).  
  
10. Altında **türü**seçin **komut**.  
  
     Sihirbazın oluşturduğu bir [CCommand](../../data/oledb/ccommand-class.md)-seçerseniz tüketici tabanlı **komut** veya [CTable](../../data/oledb/ctable-class.md)-seçerseniz tüketici tabanlı **tablo**. Nesneyi seçtikten sonra adlı tablo veya komut sınıfı, ancak adını düzenleyebilirsiniz.  
  
11. Altında **Destek**, bırakın **değişiklik**, **Ekle**, ve **Sil** kutularının.  
  
     Seçin **değişiklik**, **Ekle**, ve **Sil** değiştirme, ekleme ve satır kümesindeki kayıtları silme gerekirse desteklemek için onay kutularını. Depolayabilir ve bu verileri veri yazma hakkında daha fazla bilgi için bkz: [satır kümelerini güncelleştirme](../../data/oledb/updating-rowsets.md).  
  
12. Tıklayın **son** tüketici oluşturmak için.  
  
 Sihirbaz gösterildiği gibi bir komut ve bir kullanıcı kaydı sınıfı oluşturur [kodla](../../data/oledb/consumer-wizard-generated-classes.md). Komut sınıfının girdiğiniz ad olacaktır `Class` sihirbazda kutusuna (Bu durumda, `CProducts`), ve kullanıcı kayıt sınıfı bir adı olacaktır "*ClassName*erişimci" (Bu durumda, `CProductsAccessor`).  
  
> [!NOTE]
>  Sihirbaz, aşağıdaki satırı Products.h'a getirir:  
  
```cpp  
#error Security Issue: The connection string may contain a password  
```  
  
> [!NOTE]
>  Bu satırı önleyen tüketici uygulama engeller ve bağlantı dizenizi sabit kodlanmış parolalar için denetlenecek anımsatır. Bağlantı dizenizi denetledikten sonra bu kod satırı kaldırabilirsiniz.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sihirbaz Kullanarak bir OLE DB Tüketicisi Oluşturma](../../data/oledb/creating-an-ole-db-consumer-using-a-wizard.md)