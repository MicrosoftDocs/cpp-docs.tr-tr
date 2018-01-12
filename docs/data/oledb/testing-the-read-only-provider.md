---
title: "Salt okunur sağlayıcıyı test etme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- testing, OLE DB providers
- testing providers
- OLE DB providers, calling
- OLE DB providers, testing
ms.assetid: e4aa30c1-391b-41f8-ac73-5270e46fd712
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 438ab42a7f0f12379621a591f3b0b1eeb5930afd
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="testing-the-read-only-provider"></a>Salt Okunur Sağlayıcıyı Test Etme
Bir sağlayıcı test etmek için bir tüketici gerekir. Tüketici sağlayıcı ile eşleşebilmesi durumunda yardımcı olur. OLE DB Tüketici Şablonları OLE DB çevresinde ince bir sarmalayıcı olan ve Sağlayıcısı COM nesneleriyle eşleşir. Kaynak tüketici şablonlarıyla geldiği için bir sağlayıcıyla hata ayıklama kolaydır. Tüketici Şablonları ayrıca tüketici uygulamaları geliştirmek için çok küçük ve hızlı bir yolu değildir.  
  
 Bu konudaki örnek bir test tüketicisi için bir varsayılan MFC Uygulama Sihirbazı uygulaması oluşturur. OLE DB tüketici şablonu kodu eklenen basit bir iletişim test uygulamasıdır.  
  
### <a name="to-create-the-test-application"></a>Test uygulaması oluşturmak için  
  
1.  Üzerinde **dosya** menüsünde tıklatın **yeni**ve ardından **proje**.  
  
2.  Proje Türleri bölmesinde seçin **Visual C++ projeleri** klasör. Şablonlar bölmesinde seçin **MFC uygulaması**.  
  
3.  Proje adı girin **TestProv**ve ardından **Tamam**.  
  
     MFC Uygulama Sihirbazı görünür.  
  
4.  Üzerinde **uygulama türü** sayfasında, **tabanlı iletişim**.  
  
5.  Üzerinde **Gelişmiş Özellikler** sayfasında, **Otomasyon**ve ardından **son**.  
  
> [!NOTE]
>  Eklerseniz uygulama Otomasyon desteği gerektirmez **CoInitialize** içinde **CoInitialize**.  
  
 Görüntüleyin ve kaynak görünümünde seçerek TestProv iletişim kutusu (IDD_TESTPROV_DIALOG) düzenleyin. İletişim kutusunda bir satır kümesindeki her dize için iki liste kutusu yerleştirin. Her ikisi de bir liste kutusu seçili olduğunda, ALT + Enter tıklatarak basarak liste kutusu için sıralama özelliği devre dışı bırakma **stilleri** sekmesini tıklatın ve Temizleme **sıralama** onay kutusu. Ayrıca, yerleştirin bir **çalıştırmak** dosyayı almak için iletişim kutusunda düğme. Bitmiş TestProv iletişim kutusunun sırasıyla "Dize 1" ve "dize 2" olarak etiketlenmiş iki liste kutusu olmalıdır; Ayrıca sahip **Tamam**, **iptal**, ve **çalıştırmak** düğmeler.  
  
 İletişim kutusu sınıfında (Bu örnek TestProvDlg.h) üst bilgi dosyasını açın. Üstbilgi dosyası (dışında herhangi bir sınıf bildiriminin) için aşağıdaki kodu ekleyin:  
  
```  
////////////////////////////////////////////////////////////////////////  
// TestProvDlg.h  
  
class CProvider   
{  
// Attributes  
public:  
   char   szField1[16];  
   char   szField2[16];  
  
   // Binding Maps  
BEGIN_COLUMN_MAP(CProvider)  
   COLUMN_ENTRY(1, szField1)  
   COLUMN_ENTRY(2, szField2)  
END_COLUMN_MAP()  
};  
```  
  
 Kod sütunların satır kümesinde ne olacağını tanımlayan bir kullanıcı kaydı temsil eder. İstemci çağırdığında **DBBINDING**, hangi sütunların bağlanacağını belirtmek için bu girişleri kullanır. OLE DB Tüketici Şablonları sütunları dinamik olarak bağlamanıza imkan sağlar. COLUMN_ENTRY makroları PROVIDER_COLUMN_ENTRY istemci tarafı sürümü var. İki COLUMN_ENTRY makroları sıra, türü, uzunluğu ve veri üyesi için iki dizeyi belirtin.  
  
 Bir işleyici işlevi ekleme **çalıştırmak** CTRL tuşuna basarak ve çift düğmesi **çalıştırmak** düğmesi. Aşağıdaki kodu işleve yerleştirin:  
  
```  
///////////////////////////////////////////////////////////////////////  
// TestProvDlg.cpp  
  
void CtestProvDlg::OnRun()  
{  
   CCommand<CAccessor<CProvider> > table;  
   CDataSource source;  
   CSession   session;  
  
   if (source.Open("MyProvider.MyProvider.1", NULL) != S_OK)  
      return;  
  
   if (session.Open(source) != S_OK)  
      return;  
  
   if (table.Open(session, _T("c:\\samples\\myprov\\myData.txt")) != S_OK)  
      return;  
  
   while (table.MoveNext() == S_OK)  
   {  
      m_ctlString1.AddString(table.szField1);  
      m_ctlString2.AddString(table.szField2);  
   }  
}  
```  
  
 `CCommand`, `CDataSource`, Ve `CSession` ait olan tüm OLE DB Tüketici Şablonları için sınıflar. Her sınıf bir COM nesnesi sağlayıcısındaki taklit eder. `CCommand` Nesnesi alır `CProvider` sınıfı, üstbilgi dosyası şablon parametresi olarak bildirilmedi. `CProvider` Parametresi sağlayıcıdan verilere erişmek için kullandığınız bağlamaları temsil eder. Burada `Open` veri kaynağı, oturum ve komut için kod:  
  
```  
if (source.Open("MyProvider.MyProvider.1", NULL) != S_OK)  
   return;  
  
if (session.Open(source) != S_OK)  
   return;  
  
if (table.Open(session, _T("c:\\samples\\myprov\\myData.txt")) != S_OK)  
   return;  
```  
  
 Sınıfların her biri açmak için satırlar sağlayıcısında her COM nesnesi oluşturun. Sağlayıcı bulmak için sağlayıcının ProgID kullanın. Sistem kayıt defterinden veya MyProvider.rgs dosyasına bakarak ProgID edinebilirsiniz (sağlayıcının dizin ve arama ProgID anahtarının açın).  
  
 MyData.txt dosyası MyProv örneği ile dahil edilir. Bir bir dosya oluşturmak için bir düzenleyici kullanın ve her dize arasında ENTER tuşuna basarak dizeler, çift sayı yazın. Dosyayı taşırsanız yol adını değiştirin.  
  
 Dizesini "c:\\\samples\\\myprov\\\MyData.txt" içinde `table.Open` satır. İçine adım `Open` çağrısı, gördüğünüz Bu dize geçirilecek `SetCommandText` sağlayıcısındaki yöntemi. Unutmayın `ICommandText::Execute` bu dizeyi kullanılan yöntem.  
  
 Veri getirmek için çağrı `MoveNext` tablo üzerinde. `MoveNext`çağrıları **IRowset::GetNextRows**, `GetRowCount`, ve `GetData` işlevleri. Daha fazla satır olduğunda (diğer bir deyişle, satır kümesindeki geçerli konumu değerinden daha büyük `GetRowCount`), döngü sona erer:  
  
```  
while (table.MoveNext() == S_OK)  
{  
   m_ctlString1.AddString(table.szField1);  
   m_ctlString2.AddString(table.szField2);  
}  
```  
  
 Daha fazla satır olduğunda sağlayıcılarını döndüren Not **DB_S_ENDOFROWSET**. **DB_S_ENDOFROWSET** değeri bir hata değildir. Her zaman karşı denetlemelisiniz `S_OK` veri getirme döngüsünü iptal edin ve başarılı makrosu kullanmayın.  
  
 Artık derleme ve program test mümkün olması gerekir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Basit Salt Okunur Sağlayıcıyı Geliştirme](../../data/oledb/enhancing-the-simple-read-only-provider.md)