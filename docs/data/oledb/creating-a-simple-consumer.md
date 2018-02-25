---
title: "Basit Tüketici oluşturma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- OLE DB consumers, creating
ms.assetid: ae32d657-72ea-4db8-9839-75cb5cff68ae
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 553d4f8875812aa9453ec39e0e3223bd3463a31a
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/23/2018
---
# <a name="creating-a-simple-consumer"></a>Basit Tüketici Oluşturma
ATL Proje Sihirbazı'nı ve ATL OLE DB Tüketici Sihirbazı bir OLE DB Şablonları tüketicisi oluşturmak için kullanın.  
  
#### <a name="to-create-a-console-application-for-an-ole-db-consumer"></a>Bir konsol uygulaması için bir OLE DB Tüketicisi oluşturmak için  
  
1.  Üzerinde **dosya** menüsünde tıklatın **yeni**ve ardından **proje**.  
  
     **Yeni proje** iletişim kutusu görüntülenir.  
  
2.  Proje Türleri bölmesinde **Visual C++ projeleri** klasörünü ve ardından **Win32 Proje** Şablonlar bölmesinde simgesi. İçinde **adı** kutusunda, projenizin adını girin, örneğin, **MyCons**.  
  
3.  **Tamam**'ı tıklatın.  
  
     Win32 Proje Sihirbazı görünür.  
  
4.  Üzerinde **uygulama ayarları** sayfasında, **konsol uygulaması**ve ardından **ATL desteği ekleme**.  
  
5.  Tıklatın **son** Sihirbazı kapatmak ve projeyi oluşturmak için.  
  
 Ardından, OLE DB Tüketici nesne eklemek için ATL OLE DB Tüketici Sihirbazı'nı kullanın.  
  
#### <a name="to-create-a-consumer-with-the-atl-ole-db-consumer-wizard"></a>ATL OLE DB Tüketici Sihirbazı'yla bir tüketici oluşturmak için  
  
1.  Sınıf Görünümü'nde sağ `MyCons` projesi.  
  
2.  Kısayol menüsünde **Ekle**ve ardından **sınıfı Ekle**.  
  
     **Sınıfı Ekle** iletişim kutusu görüntülenir.  
  
3.  Kategoriler bölmesinde **Visual C++**, tıklatın **ATL OLE DB Tüketicisi** Şablonlar bölmesinde ve ardından simge **açık**.  
  
     ATL OLE DB Tüketici Sihirbazı görünür.  
  
4.  Tıklatın **veri kaynağı** düğmesi.  
  
     **Veri bağlantısı özelliklerini** iletişim kutusu görüntülenir.  
  
5.  İçinde **veri bağlantısı özelliklerini** iletişim kutusunda, aşağıdakileri yapın:  
  
    -   Üzerinde **sağlayıcı** sekmesinde, bir OLE DB sağlayıcısı belirtin.  
  
    -   Üzerinde **bağlantı** sekmesinde, sunucu adını, oturum açma kimliği ve parolası veri kaynağı ve veritabanı sunucusunda belirtin.  
  
    > [!NOTE]
    >  Bir güvenlik sorunu var. **parola kaydetmeye izin ver** özelliği **veri bağlantısı özelliklerini** iletişim kutusu. İçinde **sunucuya oturum açmak için bilgileri girin**, iki radyo düğmesi vardır: **kullanım Windows NT tümleşik güvenlik** ve **belirli bir kullanıcı adı ve parolayı kullanın**.  
  
    > [!NOTE]
    >  Seçerseniz **belirli bir kullanıcı adı ve parolayı kullanın**, parolayı kaydetme seçeneğiniz (kullanarak **parola kaydetmeye izin ver** onay kutusunu); ancak, bu seçenek güvenli değildir. Seçtiğiniz önerilir **kullanım Windows NT tümleşik güvenlik**; bu seçenek, kimliğinizi doğrulamak için Windows NT kullanır.  
  
    > [!NOTE]
    >  Windows NT tümleşik güvenlik kullanamıyorsanız, orta katman bir uygulama parolası kullanıcıdan veya parolayı korumak amacıyla güvenlik mekanizmaları ile bir konumda depolamak için kullanmanız gerekir (yerine kaynak kodunda).  
  
     Sağlayıcınızı ve diğer ayarları seçtikten sonra **Bağlantıyı Sına** önceki iletişim kutusu sayfalarında yapılan seçimleri doğrulayın. Varsa **sonuçları** kutusunu raporlarını `Test connection succeeded`, tıklatın **Tamam** veri bağlantısını oluşturmak için.  
  
     **Veritabanı nesnesi Seç** iletişim kutusu görüntülenir.  
  
6.  Ağaç denetimi tablo, görünüm veya saklı yordam seçmek için kullanın. Bu yordam amacıyla, Northwind veritabanından Products tablosunu seçin.  
  
7.  **Tamam**'ı tıklatın. ATL OLE DB Tüketici Sihirbazı'na döndürür.  
  
8.  Adlar Sihirbaz tamamlandıktan `Class` ve **.h dosyası** görünüm, tablo adını temel alarak veya depolanmaz, seçtiğiniz yordamı. İsterseniz, bu adları düzenleyebilirsiniz.  
  
9. Clear **Attributed** tüketici kod kullanarak Sihirbazı'nı oluşturur, böylece onay kutusunu [OLE DB şablon sınıfları](../../data/oledb/ole-db-consumer-templates-reference.md) varsayılan yerine [OLE DB tüketici öznitelikleri](../../windows/ole-db-consumer-attributes.md).  
  
10. Altında **türü**seçin **komutu**.  
  
     Sihirbazın oluşturduğu bir [CCommand](../../data/oledb/ccommand-class.md)-seçerseniz tüketici tabanlı **komutu** veya [CTable](../../data/oledb/ctable-class.md)-seçerseniz tüketici tabanlı **tablo**. Nesneyi seçtikten sonra adlı tablo ya da komut sınıfı, ancak adı düzenleyebilirsiniz.  
  
11. Altında **Destek**, bırakın **değişiklik**, **Ekle**, ve **silmek** onay kutularının.  
  
     Seçin **değişiklik**, **Ekle**, ve **silmek** değiştirme, ekleme ve satır kayıtlarının silme gerekirse desteklemek için onay kutularını. Verileri veri yazma hakkında daha fazla bilgi depolamak için bkz: [satır kümelerini güncelleme](../../data/oledb/updating-rowsets.md).  
  
12. Tıklatın **son** tüketici oluşturmak için.  
  
 Sihirbaz gösterildiği gibi bir komut ve bir kullanıcı kayıt sınıfı oluşturur [Tüketici Sihirbazı tarafından oluşturulan sınıflar](../../data/oledb/consumer-wizard-generated-classes.md). Komut sınıfı girdiğiniz ada sahip olacaktır `Class` Sihirbazı'nda kutusunda (Bu durumda, `CProducts`), ve kullanıcı kayıt sınıfı biçiminde bir ada sahip olacaktır "*ClassName*erişimci" (Bu durumda, `CProductsAccessor`).  
  
> [!NOTE]
>  Sihirbaz, aşağıdaki satırı Products.h'a getirir:  
  
```  
#error Security Issue: The connection string may contain a password  
```  
  
> [!NOTE]
>  Bu satırı derleme tüketici uygulamanın engeller ve sabit kodlanmış parolalar için bağlantı dizenizi denetlemenizi anımsatır. Bağlantı dizenizi denetledikten sonra bu kod satırı kaldırabilirsiniz.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sihirbaz Kullanarak bir OLE DB Tüketicisi Oluşturma](../../data/oledb/creating-an-ole-db-consumer-using-a-wizard.md)