---
title: db_command | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: vc-attr.db_command
dev_langs: C++
helpviewer_keywords: db_command attribute
ms.assetid: 714c3e15-85d7-408b-9a7c-88505c3e5d24
caps.latest.revision: "13"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: a59b7eceeafe7d158dd983936fb4cffecaf2e12f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="dbcommand"></a>db_command
OLE DB komut oluşturur.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
      [ db_command(   
   command,   
   name,   
   source_name,   
   hresult,   
   bindings,   
   bulk_fetch)  
]  
```  
  
#### <a name="parameters"></a>Parametreler  
 `command`  
 OLE DB komut metni içeren bir komut dizesi. Basit bir örnek verilmiştir:  
  
```  
[ db_command ( command = "Select * from Products" ) ]  
```  
  
 *Komutu* söz dizimi aşağıdaki gibidir:  
  
```  
binding parameter block 1  
   OLE DB command  
binding parameter block 2  
   continuation of OLE DB command  
binding parameter block 3  
...  
```  
  
 A *bağlama parametre bloğu* şu şekilde tanımlanır:  
  
 **([** `bindtype` **]** *szVar1* [*, szVar2* [, *nVar3* [,...]]] **)**  
  
 burada:  
  
 **(** veri bağlama bloğu başlangıcını işaretler.  
  
 **[** `bindtype` **]** aşağıdaki büyük küçük harf duyarsız dizeleri biridir:  
  
-   **[db_column]**  her üye değişkenleri bir satır kümesi sütununa bağlar.  
  
-   **[bindto]**  (aynı **[db_column]**).  
  
-   **[in]**  üye değişkenleri giriş parametresi olarak bağlar.  
  
-   **[out]**  üye değişkenleri çıkış parametreleri olarak bağlar.  
  
-   **[içinde out]**  üye değişkenleri giriş/çıkış parametreleri olarak bağlar.  
  
 *SzVarX* geçerli kapsam içinde bir üye değişkenine çözümler.  
  
 **)** veri bağlama bloğunun sonunu işaretler.  
  
 Komut dize gibi bir veya daha fazla tanımlayıcıları [in], [out], içeriyorsa veya [Giriş/Çıkış], **db_command** parametre eşleme oluşturur.  
  
 Bir veya daha fazla parametreleri gibi [db_column] veya [bindto], komut dizesini içeriyorsa, **db_command** bir satır kümesi ve ilişkili bu değişkenleri hizmet için bir erişimci harita oluşturur. Bkz: [db_accessor](../windows/db-accessor.md) daha fazla bilgi için.  
  
> [!NOTE]
>  [`bindtype`] sözdizimi ve `bindings` parametresi geçerli değil kullanırken **db_command** sınıf düzeyinde.  
  
 Burada, parametre blokları bağlama bazı örnekler verilmiştir. Aşağıdaki örnek bağlar `m_au_fname` ve `m_au_lname` veri üyelerine `au_fname` ve `au_lname` sütunları, sırasıyla pubs veritabanındaki yazarlar tablosunun:  
  
```  
TCHAR m_au_fname[21];  
TCHAR m_au_lname[41];  
TCHAR m_state[3] = 'CA';  
  
[db_command (  
   command = "SELECT au_fname([bindto]m_au_fname), au_lname([bindto]m_au_lname) " \  
   "FROM dbo.authors " \  
   "WHERE state = ?([in]m_state)")  
```  
  
 ]  
  
 *ad* (isteğe bağlı)  
 Tanıtıcı adı olan bir satır kümesi çalışmak için kullanın. Belirtirseniz *adı*, **db_command** belirtilen bir sınıf oluşturur *adı*, kullanılabilecek çapraz satır kümesi veya birden çok eylem sorguları yürütmek için. Belirtmezseniz, *adı*, kullanıcıya birden fazla satır sonuçları döndürmek mümkün olmayacaktır.  
  
 *source_name* (isteğe bağlı)  
 `CSession` Değişkeni veya olan bir sınıfı örneği `db_source` özniteliği uygulanmış üzerinde komutu yürütür. Bkz: [db_source](../windows/db-source.md).  
  
 **db_command** için kullanılan değişken emin olmak için denetimleri *source_name* belirtilen değişkeni olmalıdır işlevi veya genel kapsam için geçerlidir.  
  
 `hresult`(isteğe bağlı)  
 Alacak değişkeni tanımlayan `HRESULT` bu veritabanı komutu. Değişkeni yoksa özniteliği tarafından otomatik olarak eklenecek.  
  
 *bağlamaları* (isteğe bağlı)  
 OLE DB komuttan bağlama parametreleri ayırmak sağlar.  
  
 İçin bir değer belirtirseniz, `bindings`, **db_command** ilişkili değer ayrıştırır ve değil ayrıştırır [`bindtype`] parametresi. Bu kullanım, OLE DB sağlayıcısı sözdizimi kullanmanıza olanak sağlar. Ayrıştırma, parametreleri, bağlama olmadan devre dışı bırakmak için belirtmek **bağlamaları = ""**.  
  
 İçin bir değer belirtmezseniz, `bindings`, **db_command** aramakta bağlama parametre bloğu ayrıştırır '**(**', ardından **[** `bindtype` **]**  bir veya daha fazla önceden tanımlanmış C++ üye değişkenleri tarafından ardından parantez içine arkasından '**)**'. Tüm metni parantez elde edilen komuttan çıkarılır ve bu parametrelerin bu komut için sütun ve parametre bağlamaları oluşturmak için kullanılan.  
  
 *bulk_fetch*(isteğe bağlı)  
 Getirmek için satır sayısını belirten bir tamsayı değeri.  
  
 Varsayılan değer tek satır getirme belirten 1'dir (satır türü olacak [CRowset](../data/oledb/crowset-class.md)).  
  
 Toplu satır getirme 1'den büyük bir değer belirtir. Toplu satır getirme başvuran birden çok satır işleyicilerini getirme yeteneği toplu satır kümeleri için (satır türü olacak [CBulkRowset](../data/oledb/cbulkrowset-class.md) ve çağıracak `SetRows` belirtilen satır sayısı).  
  
 Varsa *bulk_fetch* birden küçükse, `SetRows` sıfır döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 **db_command** oluşturur bir [CCommand](../data/oledb/ccommand-class.md) bir komutu yürütmek için bir OLE DB tüketici tarafından kullanılan nesne.  
  
 Kullanabileceğiniz **db_command** sınıfı veya işlev kapsamıyla; ana kapsamını farktır `CCommand` nesnesi. İşlev kapsamı ile veri bağlamaları gibi işlevi sonunda sonlanır. Sınıf ve işlev kapsamı kullanımları içeren OLE DB tüketici şablonu sınıfı **CCommand <>**, ancak bağımsız şablon işlevi ve sınıf durumlarda farklılık gösterir. İşlev durumda bağlamaları bulunulacak bir **erişimci** , oluşur yerel değişkenler sınıfı kullanım Infer sırada bir `CAccessor`-türetilmiş sınıf bağımsız değişkeni olarak. Bir sınıf özniteliği kullanıldığında **db_command** birlikte çalışır **db_column**.  
  
 **db_command** bir sonuç kümesi döndürmeyen komutları yürütmek için kullanılabilir.  
  
 Tüketici özniteliği sağlayıcısı bu öznitelik bir sınıfa uyguladığında derleyici sınıfa adlandıracak \_ *YourClassName*erişimci nerede *YourClassName* verdiğiniz adı sınıf ve derleyici adlı bir sınıf oluşturur de *YourClassName*, den türetilen \_ *YourClassName*erişimcisi.  Sınıf Görünümü'nde, her iki sınıfları görürsünüz.  
  
## <a name="example"></a>Örnek  
 Bu örnek adları ve soyadları durum sütununu 'CA' eşleştiği bir tablodan seçen komutu tanımlar. **db_command** oluşturur ve üzerinde çağırabilirsiniz sihirbaz tarafından oluşturulan işlevleri gibi bir satır kümesi okur [OpenAll ve CloseAll](../data/oledb/consumer-wizard-generated-methods.md), yanı `CRowset` üye işlevleri gibi [MoveNext](../data/oledb/crowset-movenext.md).  
  
 Bu kod pubs veritabanına bağlanan kendi bağlantı dizesi sağlamanızı gerektirir. Geliştirme ortamında nasıl yapılacağı hakkında daha fazla bilgi için bkz: [nasıl yapılır: Sunucu Gezgini'nden bir veritabanına bağlanmak](http://msdn.microsoft.com/en-us/7c1c3067-0d77-471b-872b-639f9f50db74) ve [nasıl yapılır: Sunucu Gezgini/veritabanı Explorer'da yeni veri bağlantıları ekleme](http://msdn.microsoft.com/en-us/fb2f513b-ddad-4142-911e-856bba0054c8).  
  
```  
// db_command.h  
#include <atlbase.h>  
#include <atlplus.h>  
#include <atldbcli.h>  
  
#pragma once  
  
[  db_source(L"your connection string"),  
   db_command(L" \  
      SELECT au_lname, au_fname \  
      FROM dbo.authors \  
      WHERE state = 'CA'")  ]  
  
struct CAuthors {  
   // In order to fix several issues with some providers, the code below may bind  
   // columns in a different order than reported by the provider  
  
   DBSTATUS m_dwau_lnameStatus;  
   DBSTATUS m_dwau_fnameStatus;  
   DBLENGTH m_dwau_lnameLength;  
   DBLENGTH m_dwau_fnameLength;  
  
   [ db_column("au_lname", status="m_dwau_lnameStatus", length="m_dwau_lnameLength") ] TCHAR m_au_lname[41];  
   [ db_column("au_fname", status="m_dwau_fnameStatus", length="m_dwau_fnameLength") ] TCHAR m_au_fname[21];  
  
   [ db_param("7", paramtype="DBPARAMIO_INPUT") ] TCHAR m_state[3];  
  
   void GetRowsetProperties(CDBPropSet* pPropSet) {  
      pPropSet->AddProperty(DBPROP_CANFETCHBACKWARDS, true, DBPROPOPTIONS_OPTIONAL);  
      pPropSet->AddProperty(DBPROP_CANSCROLLBACKWARDS, true, DBPROPOPTIONS_OPTIONAL);  
   }  
};  
```  
  
## <a name="example"></a>Örnek  
  
```  
// db_command.cpp  
// compile with: /c  
#include "db_command.h"  
  
int main(int argc, _TCHAR* argv[]) {  
   HRESULT hr = CoInitialize(NULL);  
  
   // Instantiate rowset  
   CAuthors rs;  
  
   // Open rowset and move to first row  
   strcpy_s(rs.m_state, sizeof(rs.m_state), _T("CA"));  
   hr = rs.OpenAll();  
   hr = rs.MoveFirst();  
  
   // Iterate through the rowset  
   while( SUCCEEDED(hr) && hr != DB_S_ENDOFROWSET ) {  
      // Print out the column information for each row  
      printf("First Name: %s, Last Name: %s\n", rs.m_au_fname, rs.m_au_lname);  
      hr = rs.MoveNext();  
   }  
  
   rs.CloseAll();  
   CoUninitialize();  
}  
```  
  
## <a name="example"></a>Örnek  
 Bu örnekte `db_source` bir veri kaynağı sınıfını `CMySource`, ve `db_command` komut sınıfları `CCommand1` ve `CCommand2`.  
  
```  
// db_command_2.cpp  
// compile with: /c  
#include <atlbase.h>  
#include <atlplus.h>  
#include <atldbcli.h>  
// class usage for both db_source and db_command  
  
[  db_source(L"your connection string"),  
   db_command(L" \  
      SELECT au_lname, au_fname \  
      FROM dbo.authors \  
      WHERE state = 'CA'")  ]  
struct CMySource {  
   HRESULT OpenDataSource() {  
      return S_OK;  
   }  
};  
  
[db_command(command = "SELECT * FROM Products")]  
class CCommand1 {};  
  
[db_command(command = "SELECT FNAME, LNAME FROM Customers")]  
class CCommand2 {};  
  
int main() {  
   CMySource s;  
   HRESULT hr = s.OpenDataSource();  
   if (SUCCEEDED(hr)) {  
      CCommand1 c1;  
      hr = c1.Open(s);  
  
      CCommand2 c2;  
      hr = c2.Open(s);  
   }  
  
   s.CloseDataSource();  
}  
```  
  
## <a name="requirements"></a>Gereksinimler  
  
### <a name="attribute-context"></a>Öznitelik bağlamı  
  
|||  
|-|-|  
|**Uygulandığı öğe:**|**sınıf**, `struct`, üye, yöntem, yerel|  
|**Yinelenebilir**|Hayır|  
|**Gerekli öznitelikler**|Yok.|  
|**Geçersiz öznitelikler**|Yok.|  
  
 Öznitelik bağlamları hakkında daha fazla bilgi için bkz: [öznitelik bağlamları](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [OLE DB tüketici öznitelikleri](../windows/ole-db-consumer-attributes.md)   
 [Tek başına öznitelikler](../windows/stand-alone-attributes.md)   
