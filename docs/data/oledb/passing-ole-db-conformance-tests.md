---
title: OLE DB uygunluk testlerini geçirme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- testing, OLE DB providers
- testing providers
- conformance testing
- conformance testing [OLE DB]
- OLE DB providers, testing
ms.assetid: d1a4f147-2edd-476c-b452-0e6a0ac09891
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 0288e1517bf89ec6ff8a2067311c3641d8d7113c
ms.sourcegitcommit: 889a75be1232817150be1e0e8d4d7f48f5993af2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/30/2018
ms.locfileid: "39340922"
---
# <a name="passing-ole-db-conformance-tests"></a>OLE DB Uygunluk Testlerini Geçme
Sağlayıcıları daha tutarlı hale getirmek için veri erişim SDK'sı bir OLE DB uygunluk testlerini sunmaktadır. Testleri sağlayıcınız tüm yönlerini denetleme ve sağlayıcı beklendiği gibi makul güvence verir. OLE DB uygunluk testlerini Microsoft Data Access SDK üzerinde bulabilirsiniz. Bu bölüm, uygunluk testleri geçirmek için yapmanız gerekenler üzerinde odaklanır. OLE DB uygunluk testlerini çalıştırma hakkında daha fazla bilgi için bkz.  
  
## <a name="running-the-conformance-tests"></a>Uygunluk testlerini çalıştırma  
 Visual C++ 6.0, çok sayıda takma işlev değerleri ve özellikleri denetlemenizi izin vermek için OLE DB sağlayıcı şablonları eklendi. Bu işlevlerin çoğunu yanıt uygunluk testlerini olarak eklendi.  
  
> [!NOTE]
>  OLE DB uygunluk testlerini geçirilecek sağlayıcınız için çeşitli doğrulama işlevler eklemenize gerek.  
  
 Bu sağlayıcı iki doğrulama rutinleri gerektirir. İlk yordam `CRowsetImpl::ValidateCommandID`, satır kümesi sınıfının bir parçasıdır. Bu satır kümesi oluşturma sırasında sağlayıcı şablonları tarafından çağırılır. Örnek, tüketicilerin dizinlerini desteklemiyor bildirmek için bu yordamı kullanır. İlk çağrı `CRowsetImpl::ValidateCommandID` (sağlayıcısı kullanan Not `_RowsetBaseClass` ilişkin arabirim eşlemesini eklenen typedef `CMyProviderRowset` içinde [yer işaretleri sağlayıcı desteği](../../data/oledb/provider-support-for-bookmarks.md), uzun bir satır şablon türüne sahip değilsiniz bağımsız değişkenler). Ardından, dizin parametresi NULL değilse DB_E_NOINDEX döndürür. (Bu dizin bizi kullanmak isteyen tüketici gösterir). Komut kimlikleri hakkında daha fazla bilgi için OLE DB belirtimine bakın ve Ara `IOpenRowset::OpenRowset`.  
  
 Aşağıdaki kod `ValidateCommandID` doğrulama yordamına:  
  
```cpp
/////////////////////////////////////////////////////////////////////  
// MyProviderRS.H  
// Class: CMyProviderRowset   
  
HRESULT ValidateCommandID(DBID* pTableID, DBID* pIndexID)  
{  
   HRESULT hr = _RowsetBaseClass::ValidateCommandID(pTableID, pIndexID);  
   if (hr != S_OK)  
      return hr;  
  
   if (pIndexID != NULL)  
      return DB_E_NOINDEX;    // Doesn't support indexes  
  
   return S_OK;  
}  
```  
  
 Sağlayıcı şablonları çağrı `OnPropertyChanged` her biri bir özellik değiştiğinde yöntemi `DBPROPSET_ROWSET` grubu. Diğer grupların özellikleri işlemek isterseniz, bunları uygun nesnesine eklediğiniz (diğer bir deyişle, `DBPROPSET_SESSION` denetimleri `CMyProviderSession` sınıfı).  
  
 Kod, ilk önce özelliğin diğerine bağlı olup olmadığını görmek için denetler. Özellik zincirlendiğini değilse, ayarlar `DBPROP_BOOKMARKS` özelliği true. OLE DB belirtiminin ek C özellikleri hakkında bilgi içerir. Bu bilgileri ayrıca, özellik için başka bir zincir olup olmadığını bildirir.  
  
 Eklemek isteyebilirsiniz `IsValidValue` kodunuzda rutin. Şablonları çağrı `IsValidValue` bir özelliğini ayarlamaya çalışırken. Bir özellik değerini ayarlarken ek işleme gerekiyorsa bu yöntemi geçersiz kılarsınız. Her bir özellik kümesi için aşağıdaki yöntemlerden birini olabilir.  
  
## <a name="threading-issues"></a>İş parçacığı oluşturma sorunları  
 Varsayılan olarak, OLE DB sağlayıcısı Sihirbazı ATL OLE DB sağlayıcısı Sihirbazı'nda bir grup modelinde çalıştırmak sağlayıcı için kod oluşturur. Bu kod ile uygunluk testleri çalıştırmayı denerseniz, başlangıçta hata alırsınız. LTM.exe, OLE DB uygunluk testlerini çalıştırmak için kullanılan araç varsayılan olarak ücretsiz olduğundan bu iş parçacıklarına. OLE DB sağlayıcısı Sihirbazı kod apartman modeli performans ve kullanım kolaylığı için varsayılan olarak ayarlanır.  
  
 Bu sorunu düzeltmek için LTM değiştirebilir veya sağlayıcıyı değiştirebilirsiniz.  
  
#### <a name="to-change-ltm-to-run-in-apartment-threaded-mode"></a>İş parçacığı modu grupta çalıştırılacak LTM değiştirmek için  
  
1.  LTM ana menüde'ı **Araçları**ve ardından **seçenekleri**.  
  
2.  Üzerinde **genel** sekmesinde, iş parçacığı modeli **ücretsiz iş parçacıklı** için **Grup iş parçacıklı**.  
  
 Sağlayıcınız ücretsiz iş parçacıklı modunda çalışacak şekilde değiştirmek için:  
  
-   Sağlayıcı projenizdeki tüm örnekleri için arama `CComSingleThreadModel` değiştirin `CComMultiThreadModel`, veri kaynağı, oturum ve satır kümesi üst bilgilerinde olmalıdır.  
  
-   İş parçacığı modeli .rgs dosyanızı değiştirmek **apartman** için **hem**.  
  
-   Ücretsiz iş parçacıklı programlama (diğer bir deyişle, yazma kilidi) doğru programlama izleme kuralları.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Gelişmiş Sağlayıcı Teknikleri](../../data/oledb/advanced-provider-techniques.md)