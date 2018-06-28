---
title: COleDBRecordView sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- COleDBRecordView
- AFXOLEDB/COleDBRecordView
- AFXOLEDB/COleDBRecordView::COleDBRecordView
- AFXOLEDB/COleDBRecordView::OnGetRowset
- AFXOLEDB/COleDBRecordView::OnMove
dev_langs:
- C++
helpviewer_keywords:
- COleDBRecordView [MFC], COleDBRecordView
- COleDBRecordView [MFC], OnGetRowset
- COleDBRecordView [MFC], OnMove
ms.assetid: 98612427-c4c9-4760-b7e1-85b17448add9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 122ceb1715323e1482b2a8a8544cbe3f6270c713
ms.sourcegitcommit: f1b051abb1de3fe96350be0563aaf4e960da13c3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/27/2018
ms.locfileid: "37037863"
---
# <a name="coledbrecordview-class"></a>COleDBRecordView sınıfı
Veritabanı kayıtlarını denetimlerinde görüntüleyen bir görünüm.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class COleDBRecordView : public CFormView  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="protected-constructors"></a>Korumalı Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[COleDBRecordView::COleDBRecordView](#coledbrecordview)|Oluşturan bir `COleDBRecordView` nesnesi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[COleDBRecordView::OnGetRowset](#ongetrowset)|Standart bir döndürür `HRESULT` değeri.|  
|[COleDBRecordView::OnMove](#onmove)|Geçerli kayıt (olumsuz) veri kaynağı üzerinde güncelleştirir ve belirtilen kayda taşır (sonraki, önceki, ilk veya son).|  
  
## <a name="remarks"></a>Açıklamalar  
 Doğrudan bağlı bir form görünümü görünümdür bir `CRowset` nesnesi. Görünüm bir iletişim şablonunu kaynaktan oluşturulur ve alanlarını görüntüler `CRowset` iletişim şablonun denetimlerinde nesnesi. `COleDBRecordView` Nesne iletişim kutusu veri değişimi (DDX) kullanır ve gezinme işlevini yerleşik `CRowset`, form üzerinde denetimleri ve satır kümesi alanları arasında veri hareketini otomatik hale getirmek için. `COleDBRecordView` Ayrıca taşıma için varsayılan uygulamasını sağlar, ilk sonraki, önceki ya da son kaydını ve kayıtta şu anda Görünümü güncelleştirmek için bir arabirim.  
  
 DDX işlevleri ile kullanabileceğiniz **COleDbRecordView** veritabanı kayıt kümesinden doğrudan veri almak ve bir iletişim kutusu denetiminde görüntülemek için. Kullanmanız gereken **COleDBRecordView\***  yöntemleri (gibi `DDX_Text`) değil **DDX_Field\***  işlevleri (gibi `DDX_FieldText`) ile **COleDbRecordView** . `DDX_FieldText` ile çalışmaz **COleDbRecordView** çünkü `DDX_FieldText` bir ek bağımsız değişken türü **CRecordset\***  (için `CRecordView`) veya **CDaoRecordset\***  (için `CDaoRecordView`).  
  
> [!NOTE]
>  OLE DB tüketici şablonu sınıfları yerine veri erişim nesneleri (DAO) sınıfları ile çalışıyorsanız, bir sınıf kullanma [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) yerine. Daha fazla bilgi için bkz: [genel bakış: veritabanı programlama](../../data/data-access-programming-mfc-atl.md).  
  
 `COleDBRecordView` kullanıcının konumunu satır kümesindeki kayıt görünümü kullanıcı arabirimini güncelleştirebilmesi izler. Kullanıcının herhangi bir ucunu satır geçtiğinde, kayıt görünümü kullanıcı arabirimi nesneleri devre dışı bırakır — menü öğesi veya araç çubuğu düğmeleri gibi — taşıma için daha fazla ile aynı yönde.  
  
 Satır kümesi sınıfları hakkında daha fazla bilgi için bkz: [kullanarak OLE DB Tüketici Şablonları](../../data/oledb/ole-db-consumer-templates-cpp.md) makalesi.  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CView](../../mfc/reference/cview-class.md)  
  
 [CScrollView](../../mfc/reference/cscrollview-class.md)  
  
 [Cformview'yu](../../mfc/reference/cformview-class.md)  
  
 `COleDBRecordView`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxoledb.h  
  
##  <a name="coledbrecordview"></a>  COleDBRecordView::COleDBRecordView  
 Oluşturan bir `COleDBRecordView` nesnesi.  
  
```  
COleDBRecordView(LPCTSTR lpszTemplateName);  
COleDBRecordView(UINT nIDTemplate);
```  
  
### <a name="parameters"></a>Parametreler  
 *lpszTemplateName*  
 Bir iletişim şablonunu kaynak adı null ile sonlandırılmış bir dize içeriyor.  
  
 *nIDTemplate*  
 Bir iletişim şablonunu kaynak kimliği numarasını içerir.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir türdeki bir nesne oluştururken türetilen `COleDBRecordView`, bir görünüm nesnesi oluşturmak ve görünüm temel iletişim kutusu kaynağı tanımlamak için oluşturucular çağırma. Kaynak adı (pass bağımsız değişkeni olarak bir dize oluşturucusu için) veya (pass imzasız tamsayı bağımsız değişkeni olarak) Kimliğine göre tanımlayabilirsiniz.  
  
> [!NOTE]
>  Türetilmiş sınıf *gerekir* kendi Oluşturucusu sağlayın. Oluşturucuda Oluşturucusu çağırma `COleDBRecordView::COleDBRecordView`, kaynak adı veya bağımsız değişken olarak Kimliğine sahip.  
  
##  <a name="ongetrowset"></a>  COleDBRecordView::OnGetRowset  
 İçin bir işleyici döner **CRowset <>** kayıt görünümü ile ilişkili nesne.  
  
```  
virtual CRowset<>* OnGetRowset() = 0;  
 
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Standart bir `HRESULT` değeri.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye işlevi oluşturmak veya bir satır kümesi nesnesi edinip tanıtıcı döndürmek için geçersiz kılmanız gerekir. Kayıt görünümü sınıfınız ClassWizard ile bildirirseniz, sihirbaz varsayılan geçersiz kılma yazar. ClassWizard'ın varsayılan uygulaması varsa kayıt görünümünde depolanan satır kümesi işleyicisini döndürür. Türünde bir satır kümesi nesnesi oluşturur, varsa çağrıları ve ClassWizard ile belirtilen kendi `Open` üye tabloyu veya sorguyu çalıştırmak için işlev ve ardından nesne için bir işleyici döner.  
  
> [!NOTE]
>  MFC 7.0, Geri'yi `OnGetRowset` gösteren bir işaretçi döndürdü `CRowset`. Çağıran kodu varsa `OnGetRowset`, dönüş türü şablonlaştırılmış sınıfına değiştirmenize gerek **CRowset <>**.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCDatabase#38](../../mfc/codesnippet/cpp/coledbrecordview-class_1.cpp)]  
  
 Daha fazla bilgi ve örnekler için bkz: [kayıt görünümleri: kayıt görünümünü kullanma](../../data/using-a-record-view-mfc-data-access.md).  
  
##  <a name="onmove"></a>  COleDBRecordView::OnMove  
 Görüntü ve satır kümesi farklı bir kayıtta taşır kaydı denetimler alanları görüntüleyin.  
  
```  
virtual BOOL OnMove(UINT nIDMoveCommand);
```  
  
### <a name="parameters"></a>Parametreler  
 *nIDMoveCommand*  
 Aşağıdaki standart komut kimliği değerlerden biri:  
  
- `ID_RECORD_FIRST` — İlk kaydı kayıt kümesindeki taşıyın.  
  
- `ID_RECORD_LAST` — Son kaydı kayıt kümesinde taşır.  
  
- `ID_RECORD_NEXT` — Sonraki kayıt kümesinde taşıyın.  
  
- `ID_RECORD_PREV` — Önceki kayıt kümesinde taşıyın.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Taşıma başarılı olduğunda sıfır olmayan; taşıma isteği reddedildiyse aksi 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan uygulama uygun çağırır `Move` üye işlevini `CRowset` kayıt görünümü ile ilişkili nesne.  
  
 Varsayılan olarak, `OnMove` kullanıcı kayıt görünümünde değiştirilmesi durumunda geçerli kaydı veri kaynağında güncelleştirir.  
  
 Uygulama Sihirbazı'nı ilk kaydı, son kaydı, ileri kayıt ve önceki kayıt menü öğeleriyle menü kaynağı oluşturur. Dockable Araç çubuğu seçeneğini belirlerseniz, Uygulama Sihirbazı'nı bu komutları karşılık gelen düğmelerle bir araç çubuğu da oluşturur.  
  
 Kayıt kümesindeki son kayıt geçmiş taşırsanız, kayıt görünümü son kaydı görüntülemeye devam eder. Geriye doğru ilk kaydı taşırsanız, kayıt görünümü ilk kaydı görüntülemeye devam eder.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)



