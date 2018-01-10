---
title: "CPen sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CPen
- AFXWIN/CPen
- AFXWIN/CPen::CPen
- AFXWIN/CPen::CreatePen
- AFXWIN/CPen::CreatePenIndirect
- AFXWIN/CPen::FromHandle
- AFXWIN/CPen::GetExtLogPen
- AFXWIN/CPen::GetLogPen
dev_langs: C++
helpviewer_keywords:
- CPen [MFC], CPen
- CPen [MFC], CreatePen
- CPen [MFC], CreatePenIndirect
- CPen [MFC], FromHandle
- CPen [MFC], GetExtLogPen
- CPen [MFC], GetLogPen
ms.assetid: 93175a3a-d46c-4768-be8d-863254f97a5f
caps.latest.revision: "20"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 51ea9aadc5d5ca8fb5a5a253d2ddb5972bf0dfdc
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="cpen-class"></a>CPen sınıfı
Windows grafik cihaz arabirimi (GDI) kalem yalıtır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CPen : public CGdiObject  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CPen::CPen](#cpen)|Oluşturan bir `CPen` nesnesi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CPen::CreatePen](#createpen)|Belirtilen stilini, genişlik ve fırça özniteliklerini mantıksal yüzeysel veya geometrik kalem oluşturur ve ona iliştirir `CPen` nesnesi.|  
|[CPen::CreatePenIndirect](#createpenindirect)|Kalem stili, genişlik ve verilen renk oluşturur bir [LOGPEN](http://msdn.microsoft.com/library/windows/desktop/dd145041) yapısı ve ekleninceye `CPen` nesnesi.|  
|[CPen::FromHandle](#fromhandle)|Bir işaretçi döndüren bir `CPen` nesnesi Windows verildiğinde `HPEN`.|  
|[CPen::GetExtLogPen](#getextlogpen)|Alır bir [EXTLOGPEN](http://msdn.microsoft.com/library/windows/desktop/dd162711) yapısı temel.|  
|[CPen::GetLogPen](#getlogpen)|Alır bir [LOGPEN](http://msdn.microsoft.com/library/windows/desktop/dd145041) yapısı temel.|  
  
### <a name="public-operators"></a>Ortak İşleçler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CPen::operator HPEN](#operator_hpen)|Bağlı Windows işleyici döner `CPen` nesnesi.|  
  
## <a name="remarks"></a>Açıklamalar  
 Kullanma hakkında daha fazla bilgi için `CPen`, bkz: [grafik nesneleri](../../mfc/graphic-objects.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CGdiObject](../../mfc/reference/cgdiobject-class.md)  
  
 `CPen`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxwin.h  
  
##  <a name="cpen"></a>CPen::CPen  
 Oluşturan bir `CPen` nesnesi.  
  
```  
CPen();

 
CPen(
    int nPenStyle,  
    int nWidth,  
    COLORREF crColor);

 
CPen(
    int nPenStyle,  
    int nWidth,  
    const LOGBRUSH* pLogBrush,  
    int nStyleCount = 0,  
    const DWORD* lpStyle = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 `nPenStyle`  
 Kalem stilini belirtir. Bu parametre Oluşturucusu ilk sürümünde aşağıdaki değerlerden biri olabilir:  
  
- **PS_SOLID** düz kalem oluşturur.  
  
- **PS_DASH** kesikli kalem oluşturur. Yalnızca kalem genişliği 1 veya daha az, cihaz birimleri olduğunda geçerlidir.  
  
- **PS_DOT** noktalı kalem oluşturur. Yalnızca kalem genişliği 1 veya daha az, cihaz birimleri olduğunda geçerlidir.  
  
- **PS_DASHDOT** değişen kısa çizgi ve nokta ile kalem oluşturur. Yalnızca kalem genişliği 1 veya daha az, cihaz birimleri olduğunda geçerlidir.  
  
- **PS_DASHDOTDOT** değişen kısa çizgi ve çift nokta kalem oluşturur. Yalnızca kalem genişliği 1 veya daha az, cihaz birimleri olduğunda geçerlidir.  
  
- **PS_NULL** null kalem oluşturur.  
  
- **PS_INSIDEFRAME** sınırlayıcı dikdörtgenini belirtin Windows GDI çıkış işlevleri tarafından üretilen kapalı şekiller çerçeve içine bir satır çizer kalem oluşturur (örneğin, **elips**, **dikdörtgen** , `RoundRect`, `Pie`, ve `Chord` üye işlevleri). Bu stili sınırlayıcı dikdörtgenini belirtmeyin Windows GDI çıkış işlevleri ile kullanıldığında (örneğin, `LineTo` üye işlevi), kalem çizim alanının çerçevesi tarafından sınırlı değildir.  
  
 İkinci sürümü `CPen` Oluşturucusu türü, stil, son harf ve birleştirme öznitelikleri bileşimini belirtir. Bit düzeyinde OR işleci (&#124;) kullanarak her kategori değerleri birleştirilmelidir. Kalem türü aşağıdaki değerlerden biri olabilir:  
  
- **PS_GEOMETRIC** geometrik kalem oluşturur.  
  
- **PS_COSMETIC** yüzeysel kalem oluşturur.  
  
     İkinci sürümü `CPen` Oluşturucusu ekler için aşağıdaki kalem stiller `nPenStyle`:  
  
- **PS_ALTERNATE** her bir piksel ayarlar kalem oluşturur. (Bu stili yalnızca yüzeysel kalemler için geçerlidir.)  
  
- **PS_USERSTYLE** kullanıcı tarafından sağlanan bir stil dizisi kullanan kalem oluşturur.  
  
     Son uç aşağıdaki değerlerden biri olabilir:  
  
- **PS_ENDCAP_ROUND** uç başlıkları YUVARLA.  
  
- **PS_ENDCAP_SQUARE** uç başlıkları kare.  
  
- **PS_ENDCAP_FLAT** uç başlıkları düz.  
  
     Birleştirme, aşağıdaki değerlerden biri olabilir:  
  
- **PS_JOIN_BEVEL** birleştirmeler Eğimli.  
  
- **PS_JOIN_MITER** birleştirmeler gönye tarafından belirlenen geçerli sınırı içinde olduğunda [SetMiterLimit](http://msdn.microsoft.com/library/windows/desktop/dd145076) işlevi. Birleşim bu sınırı aşarsa, Eğimli.  
  
- **PS_JOIN_ROUND** birleştirmeler YUVARLA.  
  
 `nWidth`  
 Kalem genişliğini belirtir.  
  
-   Bu değer 0 ise ilk Oluşturucu için aygıt birimleri genişliği her zaman eşleme Modu bağımsız olarak 1 piksel sürümüdür.  
  
-   Oluşturucusu ikinci sürümü için ise `nPenStyle` olan **PS_GEOMETRIC**, mantıksal birimler cinsinden genişliği verilir. Varsa `nPenStyle` olan **PS_COSMETIC**, genişlik 1 olarak ayarlanması gerekir.  
  
 `crColor`  
 Kalem bir RGB rengi içerir.  
  
 `pLogBrush`  
 İşaret eden bir `LOGBRUSH` yapısı. Varsa `nPenStyle` olan **PS_COSMETIC**, `lbColor` üyesi `LOGBRUSH` yapısı kalemin rengini belirtir ve `lbStyle` üyesi `LOGBRUSH` yapısı ayarlanmalıdır **BS_ DÜZ**. Varsa `nPenStyle` olan **PS_GEOMETRIC**, tüm üyeleri kalem fırça özniteliklerini belirtmek için kullanılması gerekir.  
  
 `nStyleCount`  
 Doubleword birimlerindeki uzunluğu belirtir `lpStyle` dizi. Bu değer sıfır olmalıdır `nPenStyle` değil **PS_USERSTYLE**.  
  
 `lpStyle`  
 Bir dizi noktalarına doubleword değerleri. İlk değer, kullanıcı tanımlı bir stil ilk tire uzunluğunu belirtir, ikinci değer ilk alanı vb. uzunluğunu belirtir. Bu işaretçinin olmalıdır **NULL** varsa `nPenStyle` değil **PS_USERSTYLE**.  
  
### <a name="remarks"></a>Açıklamalar  
 Bağımsız değişkenler olmadan Oluşturucusu kullanırsanız, sonuç başlatmalıdır `CPen` nesnesi ile `CreatePen`, `CreatePenIndirect`, veya `CreateStockObject` üye işlevleri.  
  
 Bağımsız değişken alan oluşturucu kullanırsanız, başka hiçbir başlatma gereklidir. Bağımsız değişken içermeyen Oluşturucusu her zaman başarılı olur ancak, bir hatayla karşılaşılmazsa bağımsız değişkenlerle Oluşturucusu bir özel durum.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCDocView#99](../../mfc/codesnippet/cpp/cpen-class_1.cpp)]  
  
##  <a name="createpen"></a>CPen::CreatePen  
 Belirtilen stilini, genişlik ve fırça özniteliklerini mantıksal yüzeysel veya geometrik kalem oluşturur ve ona iliştirir `CPen` nesnesi.  
  
```  
BOOL CreatePen(
    int nPenStyle,  
    int nWidth,  
    COLORREF crColor);

 
BOOL CreatePen(
    int nPenStyle,  
    int nWidth,  
    const LOGBRUSH* pLogBrush,  
    int nStyleCount = 0,  
    const DWORD* lpStyle = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 `nPenStyle`  
 Kalem stilini belirtir. Olası değerler listesi için bkz: `nPenStyle` parametresinde [CPen](#cpen) Oluşturucusu.  
  
 `nWidth`  
 Kalem genişliğini belirtir.  
  
-   İlk sürümü için `CreatePen`, bu değer 0 ise, cihaz birimleri genişliği her zaman eşleme Modu bağımsız olarak 1 piksel olur.  
  
-   İkinci sürümü için `CreatePen`, `nPenStyle` olan **PS_GEOMETRIC**, mantıksal birimler cinsinden genişliği verilir. Varsa `nPenStyle` olan **PS_COSMETIC**, genişlik 1 olarak ayarlanması gerekir.  
  
 `crColor`  
 Kalem bir RGB rengi içerir.  
  
 `pLogBrush`  
 İşaret eden bir [LOGBRUSH](http://msdn.microsoft.com/library/windows/desktop/dd145035) yapısı. Varsa `nPenStyle` olan **PS_COSMETIC**, **lbColor** üyesi `LOGBRUSH` yapısı kalemin rengini belirtir ve `lbStyle` üyesi `LOGBRUSH` yapısı olması gerekir. kümesine **BS_SOLID**. Varsa **nPenStyle** olan **PS_GEOMETRIC**, tüm üyeleri kalem fırça özniteliklerini belirtmek için kullanılması gerekir.  
  
 `nStyleCount`  
 Doubleword birimlerindeki uzunluğu belirtir `lpStyle` dizi. Bu değer sıfır olmalıdır `nPenStyle` değil **PS_USERSTYLE**.  
  
 `lpStyle`  
 Bir dizi noktalarına doubleword değerleri. İlk değer, kullanıcı tanımlı bir stil ilk tire uzunluğunu belirtir, ikinci değer ilk alanı vb. uzunluğunu belirtir. Bu işaretçinin olmalıdır **NULL** varsa `nPenStyle` değil **PS_USERSTYLE**.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, sıfır olmayan veya yöntem başarısız olursa sıfır.  
  
### <a name="remarks"></a>Açıklamalar  
 İlk sürümü `CreatePen` kalem belirtilen stili, genişlik ve renk ile başlatır. Kalem daha sonra herhangi bir cihaz bağlamı için geçerli kalem olarak seçilebilir.  
  
 1 piksel ya da her zaman gerekir büyük genişliği sahip kalemler **PS_NULL**, **PS_SOLID**, veya **PS_INSIDEFRAME** stili.  
  
 Kalem varsa **PS_INSIDEFRAME** stili ve bir renk mantıksal renk tablosundaki eşleşmeyen bir renk kalem Titremeli renk ile çizilir. **PS_SOLID** kalem stilini kalem Titremeli renk ile oluşturmak için kullanılamaz. Stil **PS_INSIDEFRAME** aynıdır **PS_SOLID** kalem genişliği 1 küçük veya buna eşit olması durumunda.  
  
 İkinci sürümü `CreatePen` belirtilen stili, genişliğini ve fırça öznitelikleri sahip mantıksal bir yüzeysel veya geometrik kalem başlatır. Yüzeysel kalem genişliği her zaman 1'dir; Geometrik kalem genişliği her zaman world birimler cinsinden belirtilir. Bir uygulamanın mantıksal kalem oluşturduktan sonra o kalem bir cihaz bağlamına çağırarak seçebilirsiniz [CDC::SelectObject](../../mfc/reference/cdc-class.md#selectobject) işlevi. Kalem bir cihaz bağlamına seçtikten sonra çizgiler ve eğrilerle çizmek için kullanılabilir.  
  
-   Varsa `nPenStyle` olan **PS_COSMETIC** ve **PS_USERSTYLE**, girdileri `lpStyle` dizi uzunlukları çizgi ve boşluk stili birimleri belirtin. Stil birim bir çizgi çizmek için Kalem kullanıldığı aygıt tarafından tanımlanır.  
  
-   Varsa `nPenStyle` olan **PS_GEOMETRIC** ve **PS_USERSTYLE**, girdileri `lpStyle` dizi uzunlukları çizgi ve boşluk mantıksal birimler cinsinden belirtin.  
  
-   Varsa `nPenStyle` olan **PS_ALTERNATE**, stil birim göz ardı edilir ve her bir piksel ayarlayın.  
  
 Bir uygulama artık verilen kalem gerektirdiğinde çağırmalıdır [CGdiObject::DeleteObject](../../mfc/reference/cgdiobject-class.md#deleteobject) üye işlev veya destroy `CPen` kaynak artık kullanımda şekilde nesne. Cihaz bağlamında kalem seçildiğinde bir uygulama kalem silmemelisiniz.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCDocView#100](../../mfc/codesnippet/cpp/cpen-class_2.cpp)]  
  
##  <a name="createpenindirect"></a>CPen::CreatePenIndirect  
 Stil, genişlik ve gösterdiği yapısı verilen renk sahip kalem başlatır `lpLogPen`.  
  
```  
BOOL CreatePenIndirect(LPLOGPEN lpLogPen);
```  
  
### <a name="parameters"></a>Parametreler  
 `lpLogPen`  
 İşaret Windows [LOGPEN](../../mfc/reference/logpen-structure.md) kalem hakkında bilgi içeren yapısı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İşlev başarılı olursa sıfır dışında bir değer, aksi durumda 0.  
  
### <a name="remarks"></a>Açıklamalar  
 1 piksel ya da her zaman gerekir büyük genişliği sahip kalemler **PS_NULL**, **PS_SOLID**, veya **PS_INSIDEFRAME** stili.  
  
 Kalem varsa **PS_INSIDEFRAME** stili ve bir renk mantıksal renk tablosundaki eşleşmeyen bir renk kalem Titremeli renk ile çizilir. **PS_INSIDEFRAME** stili aynıdır **PS_SOLID** kalem genişliği 1 küçük veya buna eşit olması durumunda.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCDocView#101](../../mfc/codesnippet/cpp/cpen-class_3.cpp)]  
  
##  <a name="fromhandle"></a>CPen::FromHandle  
 Bir işaretçi döndüren bir `CPen` Windows GDI kalem nesnesi için bir tanıtıcı verilen nesnesi.  
  
```  
static CPen* PASCAL FromHandle(HPEN hPen);
```  
  
### <a name="parameters"></a>Parametreler  
 *hPen*  
 `HPEN`Windows GDI kalem işleyin.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir işaretçi bir `CPen` nesne başarılı; Aksi takdirde **NULL**.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsa bir `CPen` nesne tanıtıcısını, geçici bir iliştirilmemiş `CPen` nesnesi oluşturulur ve bağlı. Bu geçici `CPen` nesnesi, hangi tüm geçici grafiği zaman durdurulacağını sonraki açışınızda uygulama boşta kalma süresi, olay döngüde olana kadar nesneler silinir yalnızca geçerli. Diğer bir deyişle, geçici nesne yalnızca bir pencere ileti işleme sırasında geçerli değil.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCDocView#105](../../mfc/codesnippet/cpp/cpen-class_4.cpp)]  
  
##  <a name="getextlogpen"></a>CPen::GetExtLogPen  
 Alır bir **EXTLOGPEN** yapısı temel.  
  
```  
int GetExtLogPen(EXTLOGPEN* pLogPen);
```  
  
### <a name="parameters"></a>Parametreler  
 `pLogPen`  
 İşaret eden bir [EXTLOGPEN](http://msdn.microsoft.com/library/windows/desktop/dd162711) kalem hakkında bilgi içeren yapısı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 **EXTLOGPEN** stili, genişlik ve Kalem fırça özniteliklerini yapısını tanımlar. Örneğin, arama `GetExtLogPen` kalem belirli stilini eşleşecek şekilde.  
  
 Kalem öznitelikleri hakkında bilgi için Windows SDK'nda aşağıdaki konulara bakın:  
  
- [GetObject](http://msdn.microsoft.com/library/windows/desktop/dd144904)  
  
- [EXTLOGPEN](http://msdn.microsoft.com/library/windows/desktop/dd162711)  
  
- [LOGPEN](http://msdn.microsoft.com/library/windows/desktop/dd145041)  
  
- [ExtCreatePen](http://msdn.microsoft.com/library/windows/desktop/dd162705)  
  
### <a name="example"></a>Örnek  
 Aşağıdaki kod örneğinde arama gösterilmektedir `GetExtLogPen` bir kalem öznitelikleri almak ve yeni, yüzeysel kalem aynı renkle oluşturmak için.  
  
 [!code-cpp[NVC_MFCDocView#102](../../mfc/codesnippet/cpp/cpen-class_5.cpp)]  
  
##  <a name="getlogpen"></a>CPen::GetLogPen  
 Alır bir `LOGPEN` yapısı temel.  
  
```  
int GetLogPen(LOGPEN* pLogPen);
```  
  
### <a name="parameters"></a>Parametreler  
 `pLogPen`  
 İşaret eden bir [LOGPEN](http://msdn.microsoft.com/library/windows/desktop/dd145041) yapısı kalem hakkında bilgiler içerir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 `LOGPEN` Stili, renk ve Kalem desenini yapısını tanımlar.  
  
 Örneğin, arama `GetLogPen` kalem belirli stilini eşleşecek şekilde.  
  
 Kalem öznitelikleri hakkında bilgi için Windows SDK'nda aşağıdaki konulara bakın:  
  
- [GetObject](http://msdn.microsoft.com/library/windows/desktop/dd144904)  
  
- [LOGPEN](http://msdn.microsoft.com/library/windows/desktop/dd145041)  
  
### <a name="example"></a>Örnek  
 Aşağıdaki kod örneğinde arama gösterilmektedir `GetLogPen` kalem karakter almak ve yeni, düz kalem aynı renkle oluşturmak için.  
  
 [!code-cpp[NVC_MFCDocView#103](../../mfc/codesnippet/cpp/cpen-class_6.cpp)]  
  
##  <a name="operator_hpen"></a>CPen::operator HPEN  
 Ekli Windows GDI işleyicisini alır `CPen` nesnesi.  
  
```  
operator HPEN() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı, Windows GDI nesnesi için bir tanıtıcı tarafından temsil edilen varsa `CPen` nesne; Aksi halde **NULL**.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işleç doğrudan kullanımını destekleyen bir atama işleci olan bir `HPEN` nesnesi.  
  
 Grafik nesneleri kullanma hakkında daha fazla bilgi için bkz: [grafik nesneleri](http://msdn.microsoft.com/library/windows/desktop/dd144962) Windows SDK.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCDocView#104](../../mfc/codesnippet/cpp/cpen-class_7.cpp)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CGdiObject sınıfı](../../mfc/reference/cgdiobject-class.md)   
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [CBrush Sınıfı](../../mfc/reference/cbrush-class.md)
