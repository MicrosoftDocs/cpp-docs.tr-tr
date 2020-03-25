---
title: Salt Okunur Sağlayıcıyı Test Etme
ms.date: 11/04/2016
helpviewer_keywords:
- testing, OLE DB providers
- testing providers
- OLE DB providers, calling
- OLE DB providers, testing
ms.assetid: e4aa30c1-391b-41f8-ac73-5270e46fd712
ms.openlocfilehash: dc3c4ea36aa9dac64f2aa7861fd5d51927c77ecd
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80209514"
---
# <a name="testing-the-read-only-provider"></a>Salt Okunur Sağlayıcıyı Test Etme

Bir sağlayıcıyı test etmek için bir tüketiciye ihtiyacınız vardır. Tüketicinin sağlayıcıyla eşleşmenize yardımcı olur. OLE DB tüketici şablonları, OLE DB etrafındaki ve sağlayıcı COM nesneleriyle eşleşen ince bir sarmalayıcıdır. Kaynak tüketici şablonlarıyla birlikte gönderildiği için, bir sağlayıcıda hata ayıklamak kolay bir işlemdir. Tüketici şablonları, tüketici uygulamaları geliştirmenin çok küçük ve hızlı bir yoludur.

Bu konudaki örnek, bir test tüketicisi için varsayılan bir MFC Uygulama Sihirbazı uygulaması oluşturur. Test uygulaması OLE DB Tüketici şablonu kodu eklenmiş basit bir iletişim kutusu.

## <a name="to-create-the-test-application"></a>Test uygulaması oluşturmak için

1. **Dosya** menüsünde **Yeni**' ye ve ardından **Proje**' ye tıklayın.

1. **Proje türleri** bölmesinde, **yüklü** > **Visual C++**  > **MFC/ATL** klasörünü seçin. **Şablonlar** bölmesinde **MFC uygulaması**' nı seçin.

1. Proje adı için *TestProv*yazın ve ardından **Tamam**' a tıklayın.

   **MFC Uygulama** Sihirbazı görüntülenir.

1. **Uygulama türü** sayfasında **iletişim kutusu temelli**' yi seçin.

1. **Gelişmiş Özellikler** sayfasında **Otomasyon**' u seçin ve ardından **son**' a tıklayın.

> [!NOTE]
> `CTestProvApp::InitInstance``CoInitialize` eklerseniz uygulama Otomasyon desteği gerektirmez.

**TestProv** iletişim kutusunu (IDD_TESTPROV_DIALOG) **kaynak görünümü**' de seçerek görüntüleyebilir ve düzenleyebilirsiniz. İletişim kutusunda satır kümesindeki her bir dize için bir tane olmak üzere iki liste kutusu yerleştirin. Liste kutusu seçildiğinde **Alt**+**girin** ve **sıralama** özelliğini **false**olarak ayarlayarak her iki liste kutusu için sıralama özelliğini kapatın. Ayrıca, iletişim kutusunda dosyayı getirmek için bir **Çalıştır** düğmesi koyun. Tamamlanmış **TestProv** iletişim kutusu sırasıyla "String 1" ve "String 2" etiketli iki liste kutusuna sahip olmalıdır; Ayrıca **Tamam**, **iptal**ve **Çalıştır** düğmeleri de vardır.

İletişim kutusu sınıfı için üst bilgi dosyasını açın (Bu durumda TestProvDlg. h). Aşağıdaki kodu üstbilgi dosyasına ekleyin (herhangi bir sınıf bildiriminin dışında):

```cpp
////////////////////////////////////////////////////////////////////////
// TestProvDlg.h
#include <atldbcli.h>  

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

Kod, satır kümesinde hangi sütunların olacağını tanımlayan bir Kullanıcı kaydını temsil eder. İstemci `IAccessor::CreateAccessor`çağırdığında, hangi sütunların bağlanacağını belirtmek için bu girdileri kullanır. OLE DB tüketici şablonları sütunları dinamik olarak bağlamanıza de olanak tanır. COLUMN_ENTRY makroları PROVIDER_COLUMN_ENTRY makroların istemci tarafı sürümüdür. İki COLUMN_ENTRY makro iki dizenin sıra sayısını, türünü, uzunluğunu ve veri üyesini belirtir.

**CTRL** tuşuna basarak ve **Çalıştır** düğmesine çift tıklayarak **Çalıştır** düğmesine bir işleyici işlevi ekleyin. İşlevine aşağıdaki kodu yerleştirin:

```cpp
///////////////////////////////////////////////////////////////////////
// TestProvDlg.cpp

void CTestProvDlg::OnRun()
{
   CCommand<CAccessor<CProvider>> table;
   CDataSource source;
   CSession session;

   if (source.Open("Custom.Custom.1", NULL) != S_OK)
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

`CCommand`, `CDataSource`ve `CSession` sınıfları OLE DB tüketici şablonlarına aittir. Her sınıf, sağlayıcıdaki bir COM nesnesini taklit eder. `CCommand` nesnesi, bir şablon parametresi olarak üstbilgi dosyasında belirtilen `CProvider` sınıfını alır. `CProvider` parametresi, sağlayıcıdan veriye erişmek için kullandığınız bağlamaları temsil eder.

Sınıfların her birini açmak için satırlar, sağlayıcıdaki her bir COM nesnesini oluşturur. Sağlayıcıyı bulmak için sağlayıcının `ProgID` kullanın. `ProgID` sistem kayıt defterinden veya Custom. rgs dosyasına bakarak (sağlayıcının dizinini açıp `ProgID` anahtarını arayarak) alabilirsiniz.

MyData. txt dosyası `MyProv` örneğine dahildir. Kendi dosyanızı oluşturmak için bir düzenleyici kullanın ve her bir dize arasında **ENTER** tuşuna basarak çift sayıda dize yazın. Dosyayı taşırsanız yol adını değiştirin.

`table.Open` satırındaki "c:\\\Samples\\\myprov\\\MyData.txt" dizesini geçirin. `Open` çağrısına adımınızda, bu dizenin sağlayıcıda `SetCommandText` yöntemine geçtiğini görürsünüz. `ICommandText::Execute` yönteminin bu dizeyi kullandığına unutmayın.

Verileri getirmek için tablodaki `MoveNext` çağırın. `MoveNext` `IRowset::GetNextRows`, `GetRowCount`ve `GetData` işlevleri çağırır. Daha fazla satır olmadığında (yani, satır kümesindeki geçerli konum `GetRowCount`), döngü sonlanır.

Daha fazla satır olmadığında, sağlayıcılar DB_S_ENDOFROWSET döndürür. DB_S_ENDOFROWSET değeri bir hata değil. Veri getirme döngüsünü iptal etmek ve başarılı makroyu kullanmadan S_OK karşı her zaman göz atın.

Şimdi programı derleyip test edebilmelisiniz.

## <a name="see-also"></a>Ayrıca bkz.

[Basit Salt Okunur Sağlayıcıyı Geliştirme](../../data/oledb/enhancing-the-simple-read-only-provider.md)
