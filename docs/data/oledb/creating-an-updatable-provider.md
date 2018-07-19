---
title: Güncelleştirilebilir sağlayıcı oluşturma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- OLE DB providers, updatable
- notifications, support in providers
- OLE DB providers, creating
ms.assetid: bdfd5c9f-1c6f-4098-822c-dd650e70ab82
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: cbcd69168b70e8d85bf2b90c3f456f79cd1c228c
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/11/2018
ms.locfileid: "38954590"
---
# <a name="creating-an-updatable-provider"></a>Güncelleştirilebilir Sağlayıcı Oluşturma

Visual C++ güncelleştirilebilir sağlayıcılar veya güncelleştirebilirsiniz sağlayıcılarını destekler (yazma) veri deposu. Bu konu, OLE DB Şablonları kullanarak güncelleştirilebilir sağlayıcı oluşturma işlemini açıklar.  
  
 Bu konuda, uyumlu bir sağlayıcı ile başlayan varsayılır. Güncelleştirilebilir sağlayıcı oluşturma için iki adımı vardır. Sağlayıcı veri deposuna değişiklikleri nasıl yapacak önce karar vermeniz gerekir; Özellikle, değişiklikleri hemen yapılmasına olup bir güncelleştirme komut verilene kadar ertelendi. Bölüm "[sağlayıcıları güncelleştirilebilir yapmadan](#vchowmakingprovidersupdatable)" sağlayıcı kodunda yapmak için ihtiyacınız olan ayarları ve değişiklikleri açıklar.  
  
 Ardından, sağlayıcınız tüketici isteyebileceği desteklemek için tüm işlevselliklerini içerir emin olmanız gerekir. Tüketici veri deposunu güncelleştirin isterse, sağlayıcı veri deposunda veri devam kodu içermesi gerekir. Örneğin, veri kaynağı gibi işlemleri gerçekleştirmek için MFC ve C çalışma zamanı kitaplığı kullanabilirsiniz. Bölüm "[veri kaynağına yazma](#vchowwritingtothedatasource)" veri kaynağına yazma, uğraşmanız açıklar `NULL` varsayılan değerler ve sütun bayraklarını ayarlayın.  
  
> [!NOTE]
>  UpdatePV güncelleştirilebilir sağlayıcı örneğidir. UpdatePV MyProv ancak güncelleştirilebilir destekle aynıdır.  
  
##  <a name="vchowmakingprovidersupdatable"></a> Güncelleştirilebilir sağlayıcılar hale getirme  

 Anahtarı bir sağlayıcı güncelleştirilebilir yapmak istediğiniz veri deposuna ve bu işlemleri gerçekleştirmek için sağlayıcı istediğiniz gerçekleştirmek için sağlayıcınıza hangi işlemleri anlamaktır. Özellikle, veri deposuna güncelleştirmeleri hemen Bitti veya ertelenmiş olup önemli bir sorun olduğunu (toplanmış) güncelleştirme komut verilene kadar.  
  
 İlk devralınacak karar vermeniz gerekir `IRowsetChangeImpl` veya `IRowsetUpdateImpl` satır kümesi sınıfınızdaki. Bu uygulama seçiminize bağlı olarak, üç yöntem işlevselliği etkilenir: `SetData`, `InsertRows`, ve `DeleteRows`.  
  
- Gelen devralıyorsanız [IRowsetChangeImpl](../../data/oledb/irowsetchangeimpl-class.md), hemen bu üç yöntem çağırma veri deposu değiştirir.  
  
- Gelen devralıyorsanız [IRowsetUpdateImpl](../../data/oledb/irowsetupdateimpl-class.md), çağırana kadar yöntemleri veri deposuna değişiklikler erteleme `Update`, `GetOriginalData`, veya `Undo`. Güncelleştirme birkaç değişikliği içeriyorsa, bunlar toplu iş modunda (değişiklikleri toplu işleme önemli ölçüde Bellek Yükü ekleyebilirsiniz. Not) gerçekleştirilir.  
  
 Unutmayın `IRowsetUpdateImpl` türetildiği `IRowsetChangeImpl`. Bu nedenle, `IRowsetUpdateImpl` değiştirme yeteneği yanı sıra batch yeteneği verir.  
  
#### <a name="to-support-updatability-in-your-provider"></a>Sağlayıcınızdaki Güncelleştirilebilirlik desteklemek için  
  
1. Satır kümesi sınıfınızda devralınacak `IRowsetChangeImpl` veya `IRowsetUpdateImpl`. Bu sınıflar, veri depolama alanı değiştirmek için uygun arabirimleri sağlar:  
  
     **IRowsetChange ekleme**  
  
     Ekleme `IRowsetChangeImpl` bu formu kullanarak, devralma zincirini için:  
  
    ```  
    IRowsetChangeImpl< rowset-name, storage-name >  
    ```  
  
     Ayrıca `COM_INTERFACE_ENTRY(IRowsetChange)` için `BEGIN_COM_MAP` satır kümesi sınıfınıza bölümünde.  
  
     **IRowsetUpdate ekleme**  
  
     Ekleme `IRowsetUpdate` bu formu kullanarak, devralma zincirini için:  
  
    ```  
    IRowsetUpdateImpl< rowset-name, storage>  
    ```  
  
    > [!NOTE]
    >  Kaldırmalısınız `IRowsetChangeImpl` , devralma zincirini satırından. Bu daha önce bahsedilen yönergesi bir durum kodunu içermelidir `IRowsetChangeImpl`.  
  
2.  COM haritanıza aşağıdakileri ekleyin (`BEGIN_COM_MAP ... END_COM_MAP`):  
  
    |Uygularsanız|COM Eşlemesi Ekle|  
    |----------------------|--------------------|  
    |`IRowsetChangeImpl`|`COM_INTERFACE_ENTRY(IRowsetChange)`|  
    |`IRowsetUpdateImpl`|`COM_INTERFACE_ENTRY(IRowsetChange)COM_INTERFACE_ENTRY(IRowsetUpdate)`|  
  
3.  Özellik kümesi haritanıza komutunuza ekleyin (`BEGIN_PROPSET_MAP ... END_PROPSET_MAP`):  
  
    |Uygularsanız|Özellik kümesi haritasına Ekle|  
    |----------------------|-----------------------------|  
    |`IRowsetChangeImpl`|`PROPERTY_INFO_ENTRY_VALUE(IRowsetChange, VARIANT_FALSE)`|  
    |`IRowsetUpdateImpl`|`PROPERTY_INFO_ENTRY_VALUE(IRowsetChange, VARIANT_FALSE)PROPERTY_INFO_ENTRY_VALUE(IRowsetUpdate, VARIANT_FALSE)`|  
  
4.  Bunlar aşağıda görüldüğü gibi özellik kümesi eşlemesi, ayrıca tüm aşağıdaki ayarlardan birini içermelidir:  
  
    ```  
    PROPERTY_INFO_ENTRY_VALUE(UPDATABILITY, DBPROPVAL_UP_CHANGE |   
      DBPROPVAL_UP_INSERT | DBPROPVAL_UP_DELETE)  
    PROPERTY_INFO_ENTRY_VALUE(CHANGEINSERTEDROWS, VARIANT_TRUE)  
    PROPERTY_INFO_ENTRY_VALUE(IMMOBILEROWS, VARIANT_TRUE)  
  
    PROPERTY_INFO_ENTRY_EX(OWNINSERT, VT_BOOL, DBPROPFLAGS_ROWSET |   
      DBPROPFLAGS_READ, VARIANT_TRUE, 0)  
    PROPERTY_INFO_ENTRY_EX(OWNUPDATEDELETE, VT_BOOL, DBPROPFLAGS_ROWSET |   
      DBPROPFLAGS_READ, VARIANT_TRUE, 0)  
    PROPERTY_INFO_ENTRY_EX(OTHERINSERT, VT_BOOL, DBPROPFLAGS_ROWSET |   
      DBPROPFLAGS_READ, VARIANT_TRUE, 0)  
    PROPERTY_INFO_ENTRY_EX(OTHERUPDATEDELETE, VT_BOOL, DBPROPFLAGS_ROWSET |   
      DBPROPFLAGS_READ, VARIANT_TRUE, 0)  
    PROPERTY_INFO_ENTRY_EX(REMOVEDELETED, VT_BOOL, DBPROPFLAGS_ROWSET |   
      DBPROPFLAGS_READ, VARIANT_FALSE, 0)  
    ```  
  
     Özellik kimlikleri ve değerleri için Atldb.h bakarak bu makro çağrılarında kullanılan değerleri bulabilirsiniz (Atldb.h çevrimiçi belgelerinden farklıysa, Atldb.h belgeleri yerini alır).  
  
    > [!NOTE]
    >  Çoğu `VARIANT_FALSE` ve `VARIANT_TRUE` ayarları, OLE DB Şablonları tarafından gereklidir; OLE DB belirtimi okuma/yazma olabilirler, ancak OLE DB Şablonları, yalnızca bir değer destekleyebilir söyler.  
  
     **IRowsetChangeImpl uygularsanız**  
  
     Uygularsanız `IRowsetChangeImpl`, sağlayıcınız üzerinde aşağıdaki özellikleri ayarlayın. Bu özellikler öncelikle arabirimleri aracılığıyla istemek için kullanılan `ICommandProperties::SetProperties`.  
  
    - `DBPROP_IRowsetChange`: Bu otomatik olarak kümelerini ayarlama `DBPROP_IRowsetChange`.  
  
    - `DBPROP_UPDATABILITY`: Desteklenen yöntemlerden belirtme bir bit maskesi `IRowsetChange`: `SetData`, `DeleteRows`, veya `InsertRow`.  
  
    - `DBPROP_CHANGEINSERTEDROWS`: Tüketici çağırabilir `IRowsetChange::DeleteRows` veya `SetData` yeni eklenen satırlar için.  
  
    - `DBPROP_IMMOBILEROWS`: Satır kümesi, eklenen veya güncelleştirilen satır düzenlemez.  
  
     **IRowsetUpdateImpl uygularsanız**  
  
     Uygularsanız `IRowsetUpdateImpl`, aşağıdaki özellikleri sağlayıcınız üzerinde ayrıca tüm özelliklerini ayarlamak ayarlamanız gerekir `IRowsetChangeImpl` daha önce listelenen:  
  
    - `DBPROP_IRowsetUpdate`.  
  
    - `DBPROP_OWNINSERT`: READ_ONLY ve VARIANT_TRUE olması gerekir.  
  
    - `DBPROP_OWNUPDATEDELETE`: READ_ONLY ve VARIANT_TRUE olması gerekir.  
  
    - `DBPROP_OTHERINSERT`: READ_ONLY ve VARIANT_TRUE olması gerekir.  
  
    - `DBPROP_OTHERUPDATEDELETE`: READ_ONLY ve VARIANT_TRUE olması gerekir.  
  
    - `DBPROP_REMOVEDELETED`: READ_ONLY ve VARIANT_TRUE olması gerekir.  
  
    - `DBPROP_MAXPENDINGROWS`.  
  
        > [!NOTE]
        >  Bildirimleri destekliyorsa, bazı diğer özellikleri de da olabilir; bölümüne `IRowsetNotifyCP` bu listesi.  
  
##  <a name="vchowwritingtothedatasource"></a> Veri kaynağına yazma  
 Veri kaynağından okumak için çağrı `Execute` işlevi. Veri kaynağına yazmak için çağrı `FlushData` işlevi. (Genel olarak, bir tablo veya dizini diske yaptığınız değişiklikleri kaydetmek için yol temizler.)  

