---
description: 'Hakkında daha fazla bilgi edinin: MFC kaynak dosyalarını kullanma'
title: MFC kaynak dosyalarını kullanma
ms.date: 08/19/2019
helpviewer_keywords:
- public members
- source files
- MFC, source files
- MFC source files
- comments, MFC
- private member access
- protected member access
- source files, MFC
ms.assetid: 3230e8fb-3b69-4ddf-9538-365ac7ea5e72
ms.openlocfilehash: 42dc285bf4877c4bef70e430b6d2982f43e08d51
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97143266"
---
# <a name="using-the-mfc-source-files"></a>MFC kaynak dosyalarını kullanma

Microsoft Foundation Class (MFC) kitaplığı tam kaynak kodu sağlar. Üst bilgi dosyaları (. h), *\atlmfc\include* dizininde yer alır. Uygulama dosyaları (. cpp), *\atlmfc\src\mfc* dizininde bulunur.

Bu makalede, MFC 'nin her bir sınıfın çeşitli bölümlerine, bu açıklamaların ne anlama geldiğini ve her bölümde bulmayı beklemeniz gerekenleri açıklama eklemek için kullandığı kurallar açıklanmaktadır. Visual Studio sihirbazları, sizin için oluşturdukları sınıflar için benzer kuralları kullanır ve büyük olasılıkla kendi kodunuz için yararlı olan bu kuralları bulabilirsiniz.

**`public`**, **`protected`** Ve **`private`** C++ anahtar sözcükleriyle tanıdık olabilirsiniz. MFC başlık dosyalarında her bir sınıfın birkaç tane olabilir. Örneğin, ortak üye değişkenleri ve işlevleri, birden fazla anahtar sözcük altında olabilir **`public`** . Bunun nedeni, MFC 'nin üye değişkenlerini ve işlevleri, izin verilen erişim türüne göre değil, kullanımına göre ayırır. MFC, gelişigüzel bir şekilde kullanır **`private`** . Genellikle uygulama ayrıntıları olarak kabul edilen öğeler de **`protected`** birçok kez olur **`public`** . Uygulama ayrıntılarına erişim önerilmez, ancak MFC sizin için kararı bırakır.

MFC kaynak dosyalarında ve MFC Uygulama Sihirbazı 'Nın oluşturduğu üstbilgi dosyalarında, bu sınıf bildirimleri dahilinde (genellikle bu sırada) gibi açıklamalar bulacaksınız:

`// Constructors`

`// Attributes`

`// Operations`

`// Overridables`

`// Implementation`

## <a name="an-example-of-the-comments"></a><a name="an-example-of-the-comments"></a> Açıklamalara bir örnek

Sınıfının aşağıdaki kısmi listesi, `CStdioFile` MFC 'nin sınıf üyelerini kullanıldıkları yöntemlerle bölmek için sınıflarında kullandığı standart yorumların çoğunu kullanır:

```cpp
/*============================================================================*/
// STDIO file implementation

class CStdioFile : public CFile
{
    DECLARE_DYNAMIC(CStdioFile)

public:
// Constructors
    CStdioFile();

    // . . .

// Attributes
    FILE* m_pStream;    // stdio FILE
                        // m_hFile from base class is _fileno(m_pStream)

// Operations
    // reading and writing strings
    virtual void WriteString(LPCTSTR lpsz);
    virtual LPTSTR ReadString(_Out_writes_z_(nMax) LPTSTR lpsz, _In_ UINT nMax);
    virtual BOOL ReadString(CString& rString);

// Implementation
public:
    virtual ~CStdioFile();
#ifdef _DEBUG
    void Dump(CDumpContext& dc) const;
#endif
    virtual ULONGLONG GetPosition() const;
    virtual ULONGLONG GetLength() const;
    virtual BOOL Open(LPCTSTR lpszFileName, UINT nOpenFlags, CFileException* pError = NULL);

    // . . .

protected:
    void CommonBaseInit(FILE* pOpenStream, CAtlTransactionManager* pTM);
    void CommonInit(LPCTSTR lpszFileName, UINT nOpenFlags, CAtlTransactionManager* pTM);
};
```

Bu açıklamalar, sınıf bildiriminin benzer tür sınıf üyelerini içeren bölümlerini sürekli olarak işaretler. Kuralların ayarlanmayacağını, MFC kuralları olduğunu unutmayın.

## <a name="-constructors-comment"></a>Oluşturucular yorumu

`// Constructors`MFC sınıf bildiriminin bölümü, oluşturucuları (C++ Sense) ve nesneyi gerçekten kullanması için gereken başlatma işlevlerini bildirir. Örneğin, `CWnd::Create` Oluşturucu, nesneyi kullanmadan önce, önce `CWnd` C++ oluşturucusunu çağırarak ve sonra işlevi çağırarak "tam oluşturulmuş" olması gerekir `Create` . Genellikle, bu Üyeler geneldir.

Örneğin, sınıf `CStdioFile` beş oluşturucuya sahiptir ve bunlardan biri, [yorumların bir örneği](#an-example-of-the-comments)altındaki listede gösterilir.

## <a name="-attributes-comment"></a>Öznitelikler açıklaması

`// Attributes`MFC sınıf bildiriminin bölümü nesnenin ortak özniteliklerini (veya özelliklerini) içerir. Öznitelikler genellikle üye değişkenlerdir veya Get/Set işlevleridir. "Get" ve "set" işlevleri sanal olabilir veya olmayabilir. Çoğu durumda yan etkileri olmadığı için, "Get" işlevleri genellikle vardır **`const`** . Bu üyeler genellikle geneldir. Korunan ve özel öznitelikler genellikle uygulama bölümünde bulunur.

Sınıfın örnek listesinde `CStdioFile` , [yorumların bir örneği](#an-example-of-the-comments)altında, liste *m_pStream* bir üye değişkeni içerir. Sınıf, `CDC` Bu açıklamanın altındaki yaklaşık 20 üyeyi listeler.

> [!NOTE]
> Ve gibi büyük sınıflar, `CDC` `CWnd` tek bir gruptaki tüm öznitelikleri listelemek için çok sayıda üyenin daha fazla açıklık eklememesine neden olabilir. Bu gibi durumlarda, sınıf kitaplığı diğer açıklamaları, üyeleri daha fazla belirtmek için başlıklar olarak kullanır. Örneğin,, `CDC` , `// Device-Context Functions` `// Drawing Tool Functions` `// Drawing Attribute Functions` ve daha fazlasını kullanır. Öznitelikleri temsil eden gruplar, yukarıda açıklanan normal sözdizimini izler. Birçok OLE sınıfının adlı bir uygulama bölümü vardır `// Interface Maps` .

## <a name="-operations-comment"></a>İşlem açıklaması

`// Operations`BIR MFC sınıf bildiriminin bölümü, nesneleri gerçekleştirmek veya eylemler gerçekleştirmek (işlemler gerçekleştirmek) için, nesne üzerinde çağrtabileceğiniz üye işlevlerini içerir. Genellikle yan etkileri olan bu işlevler genellikle değildir **`const`** . Bu, sınıfının ihtiyaçlarına bağlı olarak sanal veya sanal olmayan olabilirler. Genellikle, bu Üyeler geneldir.

Sınıfın örnek listesinde `CStdioFile` , [yorumların bir örneğinde](#an-example-of-the-comments), liste bu yorum altında üç üye işlev içerir: `WriteString` ve öğesinin iki aşırı yüklemesi `ReadString` .

Özniteliklerde olduğu gibi, işlemler de daha alt ayrılabilir.

## <a name="-overridables-comment"></a>Geçersiz kılınan bir açıklama

`// Overridables`MFC sınıf bildiriminin bölümü, temel sınıf davranışını değiştirmeniz gerektiğinde türetilmiş bir sınıfta geçersiz kılabileceğiniz sanal işlevler içerir. Bunlar genellikle "açık" olarak adlandırılır, ancak kesinlikle gerekli değildir. Buradaki işlevler geçersiz kılınacaktır ve genellikle "geri çağırma" veya "kanca" için bir sıralama uygular veya sağlar. Genellikle, bu Üyeler korunur.

MFC 'nin kendisinde, saf sanal işlevler her zaman bu bölüme yerleştirilir. C++ ' ta saf bir sanal işlev şu şekilde formu alır:

`virtual void OnDraw( ) = 0;`

Sınıfın örnek listesinde `CStdioFile` , [yorumların bir örneğinde](#an-example-of-the-comments), listede hiçbir geçersiz kılınan bölüm yoktur. Sınıfında `CDocument` , diğer yandan yaklaşık 10 geçersiz kılınabilir üye işlevi listelenir.

Bazı sınıflarda, yorumu da görebilirsiniz `// Advanced Overridables` . Bu işlevler yalnızca gelişmiş programcıların geçersiz kılmayı denemelidir. Büyük olasılıkla bunları geçersiz kılmalısınız.

> [!NOTE]
> Bu makalede açıklanan kurallar, genellikle otomasyon (eski adıyla OLE Otomasyonu) yöntemleri ve özellikleri için de iyi çalışır. Otomasyon yöntemleri MFC işlemlerine benzerdir. Otomasyon özellikleri MFC özniteliklerine benzerdir. Otomasyon olayları (eskiden OLE denetimleri olarak bilinen ActiveX denetimleri için desteklenir) MFC geçersiz kılınabilir üye işlevlerine benzerdir.

## <a name="-implementation-comment"></a>Uygulama açıklaması

Bu `// Implementation` bölüm, herhangi BIR MFC sınıf bildiriminin en önemli parçasıdır.

Bu bölüm tüm uygulama ayrıntılarının barındırıldığı. Bu bölümde hem üye değişkenleri hem de üye işlevleri görünebilirler. Bu satırın altındaki her şey, daha sonraki bir MFC sürümünde değişebilir. Bunu önlemenize kadar, satırın altındaki ayrıntılara güvenmemelisiniz `// Implementation` . Ayrıca, uygulama satırının altında belirtilen Üyeler açıklanmamıştır, ancak bazı uygulama teknik notlarda ele alınmıştır. Temel sınıftaki sanal işlevlerin geçersiz kılmaları, temel sınıf işlevinin hangi bölümden tanımlandığından bağımsız olarak bu bölümde bulunur. Bir işlev temel sınıf uygulamasını geçersiz kıldığında, uygulama ayrıntısı olarak kabul edilir. Genellikle, bu Üyeler korunur, ancak her zaman değildir.

`CStdioFile` [Açıklamaların bir örneği](#an-example-of-the-comments)altındaki listede, açıklama altında belirtilen Üyeler, `// Implementation` veya olarak bildirilemez **`public`** **`protected`** **`private`** . Gelecekte değiştirebilecekleri için bu üyeleri yalnızca dikkatli kullanın. **`public`** Sınıf Kitaplığı uygulamasının doğru çalışması için bir üye grubunu olarak bildirmek gerekli olabilir. Ancak, bu şekilde, belirtilen üyeleri güvenli şekilde kullanabileceğiniz anlamına gelmez.

> [!NOTE]
> Açıklamanın üzerinde ya da altında kalan türlerin açıklamalarını bulabilirsiniz `// Implementation` . Her iki durumda da, bunların altında bildirildiği üye türlerini tanımlarlar. Açıklamanın altında gerçekleştiklerinde `// Implementation` , üyelerin daha sonrakı MFC sürümlerinde değişebileceğini varsaymalısınız.

## <a name="see-also"></a>Ayrıca bkz.

[Genel MFC konuları](../mfc/general-mfc-topics.md)
