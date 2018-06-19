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
ms.openlocfilehash: 11677e6295956de768c7ebc0c113d775b066bb0c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33110470"
---
# <a name="passing-ole-db-conformance-tests"></a>OLE DB Uygunluk Testlerini Geçme
Sağlayıcıları daha tutarlı hale getirmek için OLE DB uygunluk testlerini bir dizi Veri Erişim SDK'sı sağlar. Testleri sağlayıcınız tüm yönlerini kontrol edin ve sağlayıcı beklendiği gibi ilişkin makul güvence verir. OLE DB uygunluk testlerini Microsoft Data Access SDK üzerinde bulabilirsiniz. Bu bölümde uygunluk testlerini geçmesi için yapmanız gereken şeylere odaklanmıştır. OLE DB uygunluk testlerini çalıştırma hakkında daha fazla bilgi için bkz.  
  
## <a name="running-the-conformance-tests"></a>Uygunluk testleri çalıştırma  
 Visual C++ 6.0 takma işlevleri, değerler ve özelliklerini kontrol etmenize izin vermek için OLE DB sağlayıcı şablonları eklendi. Bu işlevlerin çoğu yanıt uygunluk testleri olarak eklendi.  
  
> [!NOTE]
>  OLE DB uygunluk testlerini geçmesi sağlayıcınız için birkaç doğrulama işlevi eklemeniz gerekir.  
  
 Bu sağlayıcı iki doğrulama yordamı gerektirir. İlk yordam `CRowsetImpl::ValidateCommandID`, satır kümesi sınıfınızın bir parçasıdır. Satır kümesi oluşturma sırasında sağlayıcı şablonları tarafından adı verilir. Örnek dizinleri desteklemiyor tüketicileri bildirmek için bu yordamı kullanır. İlk çağrı `CRowsetImpl::ValidateCommandID` (sağlayıcının kullandığı Not **_RowsetBaseClass** için arabirim eşlemesine eklenen typedef `CMyProviderRowset` içinde [yer işaretleri sağlayıcı desteği](../../data/oledb/provider-support-for-bookmarks.md), gerek yoktur uzun bir satır şablon değişkenlerini yazın). Ardından, dönüş **DB_E_NOINDEX** dizin parametresi değilse **NULL** (Bu dizin bizi kullanmak isteyen tüketici gösterir). Komut kimlikleri hakkında daha fazla bilgi için OLE DB belirtimine bakın ve Ara **IOpenRowset::OpenRowset**.  
  
 Aşağıdaki kodu **ValidateCommandID** doğrulama yordamını:  
  
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
  
 Sağlayıcı şablonları çağrısı `OnPropertyChanged` birinin üzerindeki her bir özellik değiştiğinde yöntemi **DBPROPSET_ROWSET** grubu. Diğer grupların özelliklerini işlemek istiyorsanız, bunları uygun nesneye eklediğiniz (diğer bir deyişle, **DBPROPSET_SESSION** denetimleri `CMyProviderSession` sınıfı).  
  
 Kod ilk özelliği diğerine bağlı olup olmadığını görmek için denetler. Bu ayarlar, bu özelliğe zincirleme varsa **DBPROP_BOOKMARKS** özelliğinin True. Ek C OLE DB belirtiminin özellikleri hakkında bilgi içerir. Bu bilgiler aynı zamanda, özellik için başka bir zincir olup olmadığını bildirir.  
  
 Eklemek isteyebilirsiniz `IsValidValue` yordamını kodunuza. Şablonları çağrısı `IsValidValue` bir özellik Ayarla girişiminde bulunulduğunda. Bir özellik değerini ayarlarken ek işleme gerekiyorsa bu yöntemi geçersiz kılarsınız. Her bir özellik kümesi için aşağıdaki yöntemlerden birini olabilir.  
  
## <a name="threading-issues"></a>İş parçacığı oluşturma sorunları  
 Varsayılan olarak, OLE DB Sağlayıcı Sihirbazı ATL OLE DB Sağlayıcı Sihirbazı'nda bir grup modelinde çalıştırmak sağlayıcı için kod oluşturur. Bu kodu uyumluluk testleriyle çalıştırmayı denerseniz, başlangıçta hata alırsınız. LTM.exe, OLE DB uygunluk testlerini çalıştırmak için kullanılan araçtır varsayılan olarak boş olmadığından bu iş parçacığına sahip. OLE DB Sağlayıcı Sihirbazı kodu apartman modeli performans ve kullanım kolaylığı için varsayılan olarak ayarlanır.  
  
 Bu sorunu düzeltmek için LTM değiştirin veya sağlayıcıyı değiştirebilirsiniz.  
  
#### <a name="to-change-ltm-to-run-in-apartment-threaded-mode"></a>İş parçacığı modu grupta çalıştırmak için LTM değiştirmek için  
  
1.  LTM ana menüde'ı **Araçları**ve ardından **seçenekleri**.  
  
2.  Üzerinde **genel** sekmesi, iş parçacığı modeli Değiştir **ücretsiz iş parçacıklı** için **Grup iş parçacıklı**.  
  
 Sağlayıcınız ücretsiz iş parçacıklı modunda çalışacak şekilde değiştirmek için:  
  
-   Sağlayıcı projenizdeki tüm örnekleri için arama `CComSingleThreadModel` ve bunların yerine `CComMultiThreadModel`, veri kaynağı, oturum ve satır kümesi üst bilgilerinde olmalıdır.  
  
-   İş parçacığı modeli .rgs dosyanızda değiştirme **grup** için **her ikisi de**.  
  
-   İzleme doğru programlama ücretsiz iş parçacıklı programlama (diğer bir deyişle, yazma kilidi) kuralları.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Gelişmiş Sağlayıcı Teknikleri](../../data/oledb/advanced-provider-techniques.md)