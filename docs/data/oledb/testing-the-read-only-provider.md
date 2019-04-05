---
title: Salt Okunur Sağlayıcıyı Test Etme
ms.date: 11/04/2016
helpviewer_keywords:
- testing, OLE DB providers
- testing providers
- OLE DB providers, calling
- OLE DB providers, testing
ms.assetid: e4aa30c1-391b-41f8-ac73-5270e46fd712
ms.openlocfilehash: a9601b2afe40133a5cc88589b530b5ed549ac81e
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59025136"
---
# <a name="testing-the-read-only-provider"></a>Salt Okunur Sağlayıcıyı Test Etme

Bir sağlayıcı test etmek için bir tüketici gerekir. Müşteri ve sağlayıcı ile eşleşebilir varsa yardımcı olur. OLE DB Tüketici Şablonları, OLE DB çevresinde ince bir sarmalayıcı olan ve sağlayıcı COM nesneleriyle eşleşir. Kaynak tüketici şablonlarıyla birlikte sevk edilir çünkü bir sağlayıcıyla hata ayıklamak kolaydır. Tüketici uygulamaları geliştirmek için çok küçük ve daha hızlı bir şekilde Tüketici şablonları da var.

Bu konudaki örnek, bir test tüketici için bir varsayılan MFC Uygulama Sihirbazı uygulaması oluşturur. OLE DB tüketici şablonu kod eklendi içeren basit bir iletişim kutusu test uygulamasıdır.

## <a name="to-create-the-test-application"></a>Test uygulaması oluşturmak için

1. Üzerinde **dosya** menüsünde tıklatın **yeni**ve ardından **proje**.

1. İçinde **proje türleri** bölmesinde **yüklü** > **Visual C++** > **MFC/ATL** klasör. İçinde **şablonları** bölmesinde **MFC uygulaması**.

1. Proje adı olarak *TestProv*ve ardından **Tamam**.

   **MFC uygulaması** Sihirbazı görünür.

1. Üzerinde **uygulama türü** sayfasında **iletişim kutusu tabanlı**.

1. Üzerinde **Gelişmiş Özellikler** sayfasında **Otomasyon**ve ardından **son**.

> [!NOTE]
> Uygulamayı Otomasyon desteği gerektirmez eklerseniz `CoInitialize` içinde `CTestProvApp::InitInstance`.

Görüntüleyebileceği ve düzenleyebileceği **TestProv** içinde seçerek iletişim kutusu (IDD_TESTPROV_DIALOG) **kaynak görünümü**. İki liste kutuları satır kümesindeki her dize için bir iletişim kutusuna yerleştirin. Sıralama özelliği devre dışı hem de tuşlarına basarak liste kutusu için kapatma **Alt**+**Enter** liste kutusu seçildiğinde ve ayarı **sıralama** özelliğini**False**. Ayrıca, yerleştirin bir **çalıştırmak** dosyasını getirmek için iletişim kutusundaki düğmesi. Tamamlanmış **TestProv** iletişim kutusu, "Dize 1" ve "2 dize" etiketli, sırasıyla iki liste kutuları olmalıdır; ayrıca **Tamam**, **iptal**, ve **çalıştırın**  düğmeler.

(Bu durum TestProvDlg.h) de iletişim kutusu sınıfı için üst bilgi dosyası açın. Üst bilgi dosyası (dışında herhangi bir sınıf bildiriminin) için aşağıdaki kodu ekleyin:

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

Kod sütunların satır kümesinde ne olacağını tanımlayan bir kullanıcı kaydı gösterir. İstemci çağırdığında `IAccessor::CreateAccessor`, hangi sütunların bağlanacağını belirtmek için bu girişlerin kullanır. OLE DB Tüketici Şablonları sütunları dinamik olarak bağlama sağlar. PROVIDER_COLUMN_ENTRY istemci tarafı sürümü COLUMN_ENTRY makrolardır. İki COLUMN_ENTRY makroları, sıra, türü, uzunluğu ve veri üyesi için iki dizeyi belirtin.

Bir işleyici işlevi ekleme **çalıştırma** düğmesine basarak **Ctrl** ve çift **çalıştırma** düğmesi. Aşağıdaki kodu işleve yerleştirin:

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

`CCommand`, `CDataSource`, Ve `CSession` ait tüm OLE DB Tüketici Şablonları için sınıflar. Her sınıf, bir COM nesnesi sağlayıcısındaki taklit eder. `CCommand` Nesnesi alır `CProvider` sınıfı, üst bilgi dosyasında, bir şablon parametresi olarak bildirilmiş. `CProvider` Parametresini sağlayıcıdan verilere erişmek için kullandığınız bağlamaları temsil eder. 

Sınıfların her birini açmak için satırlar sağlayıcıda her COM nesnesi oluşturur. Sağlayıcı bulmak için kullanmak `ProgID` sağlayıcısı. Alabileceğiniz `ProgID` sistem kayıt defterinden veya Custom.rgs dosyasında bakarak (sağlayıcının dizinini açın ve arama `ProgID` anahtar).

MyData.txt dosyası ile birlikte gelir `MyProv` örnek. Bir dosya, kendi kullanımı bir düzenleyici oluşturmak ve bir çift sayı dizeleri tuşuna basarak yazın **Enter** arasındaki her dize. Dosya taşırsanız, yol adını değiştirin.

Dizesini "c:\\\samples\\\myprov\\\MyData.txt" içinde `table.Open` satır. İçine adım `Open` çağrısı gördüğünüz Bu dize geçirilecek `SetCommandText` sağlayıcısındaki yöntemi. Unutmayın `ICommandText::Execute` o dizeyi kullanılan yöntem.

Verileri getirmek için çağrı `MoveNext` tablosunda. `MoveNext` çağrıları `IRowset::GetNextRows`, `GetRowCount`, ve `GetData` işlevleri. Daha fazla satır olduğunda (diğer bir deyişle, satır kümesi geçerli konumda büyüktür `GetRowCount`), bir döngüyü sonlandırır.

Daha fazla satır olduğunda, sağlayıcıları DB_S_ENDOFROWSET döndürür. DB_S_ENDOFROWSET değeri bir hata değil. Her zaman veri getirme döngüsünü iptal etme ve SUCCEEDED makrosu kullanmamak için S_OK karşı denetlemeniz gerekir.

Şimdi yapı ve test programı mümkün olması gerekir.

## <a name="see-also"></a>Ayrıca bkz.

[Basit Salt Okunur Sağlayıcıyı Geliştirme](../../data/oledb/enhancing-the-simple-read-only-provider.md)