---
title: Dynaset | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- ODBC recordsets, dynasets
- ODBC cursor library [ODBC], dynasets
- keyset-driven cursors in dynasets
- cursors [ODBC], keyset-driven cursors in dynasets
- cursor library [ODBC], dynaset availability
- recordsets [C++], dynasets
- dynasets
ms.assetid: 2867e6be-208e-4fe7-8bbe-b8697cb1045c
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 1b94957d4402eda467dbe5bb20d6522e123f2e34
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="dynaset"></a>Dynaset
Bu konuda açıklamakta ve anlatılmaktadır kendi [kullanılabilirlik](#_core_availability_of_dynasets).  
  
> [!NOTE]
>  MFC ODBC sınıfları dahil olmak üzere, bu konu geçerlidir [CRecordset](../../mfc/reference/crecordset-class.md). DAO sınıfları dynasets hakkında daha fazla bilgi için bkz: [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md). DAO ile dynaset türündeki kayıt kümelerini açabilirsiniz.  
  
 Bir dinamik dinamik özelliklere sahip bir kayıt kümesidir. Yaşam süresi boyunca, bir kayıt kümesi nesnesi dynaset modunda (genellikle bir dinamik olarak da adlandırılır) aşağıdaki şekilde veri kaynağı ile eşitlenmiş kalır. Çok kullanıcılı bir ortamda, diğer kullanıcıların düzenleyebilir veya kümenizdeki kayıtları silme veya kayıtları kümenize temsil ettiği tabloya ekleyebilirsiniz. Uygulamanızın ekler veya kayıt kümesinden sildiği kayıtları kümenize yansıtılır. Tabloya diğer kullanıcı ekleme kayıtları yansıtılmaz kümenize çağırarak dynaset yeniden yapılandırmadan kendi **Requery** üye işlevi. Diğer kullanıcıların kayıtları sildiğinizde, MFC kodu kayıt silme işlemlerini atlar. Etkilenen kayda kaydırma hemen diğer kullanıcıların varolan kayıtları düzenleme değişiklikleri kümenize yansıtılır.  
  
 Benzer şekilde, dinamik küme kayıtlarında yaptığınız düzenlemeler kullanımda dinamik kümeler diğer kullanıcılar tarafından yansıtılır. Kendi dynasets requery kadar eklediğiniz kayıtlar diğer kullanıcıların dynasets yansıtılmaz. Sildiğiniz kayıtlar "diğer kullanıcıların kayıt kümeleri içinde silinmiş"olarak işaretlenir. Aynı veritabanının birden çok bağlantı varsa (birden çok `CDatabase` nesneler), bu bağlantıları ile ilişkilendirilen kayıt kümeleri diğer kullanıcıların kayıt kümeleri aynı duruma sahip.  
  
 Dinamik kümeler en değerli alındığında veri bir hava yolu rezervasyon sistemini (örneğin olarak) dinamik olması gerekir.  
  
> [!NOTE]
>  ODBC imleç kitaplığı yüklenmesi gereken ve dinamik kümeler kullanmak için bir ODBC sürücüsü dinamik kümeleri destekleyen veri kaynağınız için sahip olmalıdır. Daha fazla bilgi için bkz: [dinamik kümeler kullanılabilirlik](#_core_availability_of_dynasets).  
  
 Kayıt bir dynaset olduğunu belirtmek için geçirmek **CRecordset::dynaset** ilk parametre olarak **açık** kayıt kümesi nesnenizin üye işlevi.  
  
> [!NOTE]
>  Güncelleştirilebilir dynaset'ler için ODBC sürücüsü ya da konumlandırılmış güncelleştirme deyimleri desteklemesi gerekir veya **:: SQLSetPos** ODBC API işlevi. Her ikisi de destekleniyorsa, MFC kullanan **:: SQLSetPos** verimlilik.  
  
##  <a name="_core_availability_of_dynasets"></a>Dinamik kümeler kullanılabilirliği  
 Aşağıdaki gereksinimler karşılanırsa MFC veritabanı sınıfları dinamik kümeler destekler:  
  
-   ODBC imleç kitaplığı DLL bu veri kaynağı için kullanımda olmamalıdır.  
  
     İmleç Kitaplığı kullanılırsa, bazı işlevler dynaset desteği için gerekli olan temel ODBC sürücüsü maskeleri. Dinamik kümeler kullanmak istiyorsanız (ve ODBC sürücüsü dinamik kümeler için gereken işlevleri bu bölümün geri kalanında açıklandığı gibi varsa), MFC oluşturduğunuzda imleç kitaplığı yüklenmemesine neden olabilir bir `CDatabase` nesnesi. Daha fazla bilgi için bkz: [ODBC](../../data/odbc/odbc-basics.md) ve [OpenEx](../../mfc/reference/cdatabase-class.md#openex) veya [açık](../../mfc/reference/cdatabase-class.md#open) sınıfının üye işlevini `CDatabase`.  
  
     ODBC terminolojisinde dinamik kümeler ve anlık görüntüleri için işaretçiler olarak adlandırılır. İmleç, bir kayıt kümesi içindeki konumunu izlemek için kullanılan bir düzenektir.  
  
-   Veri kaynağınız için ODBC sürücüsü anahtar kümesi temelli imleçler desteklemesi gerekir.  
  
     Anahtar kümesi temelli imleçler veri alma ve anahtar depolama tablodan yönetin. Anahtarlar, kullanıcının belirli bir kayda kaydırdığında tablodan geçerli verileri almak için kullanılır. Sürücünüzün bu desteği sağlayıp sağlamadığını belirlemek için arama **:: SQLGetInfo** ODBC API işleviyle **çağırın** parametresi.  
  
     Dynaset anahtar kümesi desteği olmadan açmaya çalışırsanız, size bir `CDBException` dönüş kodu değerini ile **AFX_SQL_ERROR_DYNASET_NOT_SUPPORTED**.  
  
-   ODBC sürücüsü veri kaynağınız için genişletilmiş getirme desteklemesi gerekir.  
  
     Genişletilmiş getirme yanı sıra geriye doğru kaydırmak SQL sorgusu içindeki elde edilen kayıtları iletmek yeteneğidir. Sürücünüzün bu yeteneği destekleyip desteklemediğini belirlemek için arama **:: SQLGetFunctions** ODBC API işleviyle **çağırın** parametresi.  
  
 Güncelleştirilebilir dinamik kümeler (veya bu anlık görüntüler) isterseniz, ODBC sürücüsü de ya da desteklemelidir **:: SQLSetPos** ODBC API işlevini veya konumlandırılmış güncelleştirmeler. **:: SQLSetPos** işlevi SQL deyimleri göndermeden veri kaynağını güncelleştirmek MFC izin verir. Bu destek varsa, MFC SQL kullanarak güncelleştirmeler yapmak yerine kullanır. Sürücünüzün destekleyip desteklemediğini belirlemek için **:: SQLSetPos**, çağrı **:: SQLGetInfo** ile **öğesini** parametresi.  
  
 Konumlandırılmış güncelleştirmeler SQL sözdizimini kullanır (formun **WHERE CURRENT OF** \<imleçadı >) veri kaynağında tablosundaki belirli bir satır tanımlamak için. Sürücünüzün konumlandırılmış güncelleştirmeler destekleyip desteklemediğini belirlemek için arama **:: SQLGetInfo** ile **SQL_POSITIONED_STATEMENTS** parametresi.  
  
 Genellikle, Düzey 2 API uygunluğu ile bir ODBC sürücüsü MFC dinamik kümeler (ancak değil salt iletme kayıt kümeleri) gerektirir. Veri kaynağınıza sürücüsü düzey 1 API kümesine uyuyorsa, hem güncelleştirilebilir ve salt okunur anlık görüntüler ve salt iletme kayıt kümeleri, ancak dinamik kümeleri kullanmaya devam edebilirsiniz. Ancak, düzey 1 sürücüsü genişletilmiş getirme destekliyorsa dinamik kümeler ve anahtar kümesi temelli imleçler destekleyebilir. ODBC Uyumluluk düzeyleri hakkında daha fazla bilgi için bkz: [ODBC](../../data/odbc/odbc-basics.md).  
  
> [!NOTE]
>  Anlık görüntüler ve dinamik kümeler kullanmak istiyorsanız, bunları iki farklı temel gerekir `CDatabase` nesneleri (iki farklı bağlantı).  
  
 İçin kaydırma hemen ODBC imleç kitaplığı tarafından tutulan Ara depolama kullanan anlık görüntüleri, doğrudan veri kaynağından bir kayıt dynaset'ler getirin. Bu veri kaynağı ile eşitlenmiş dynaset tarafından başlangıçta seçilen kayıtları tutar.  
  
 Visual C++'ın bu sürümünde bulunan sürücülerin listesini ve ek sürücüler edinme hakkında bilgi için bkz: [ODBC sürücü listesi](../../data/odbc/odbc-driver-list.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Açık veritabanı bağlantısı (ODBC)](../../data/odbc/open-database-connectivity-odbc.md)