---
title: Şema satır kümesi sınıfları ve Typedef sınıfları | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- vc.templates.ole
dev_langs:
- C++
helpviewer_keywords:
- schema rowsets, classes
ms.assetid: 4bd881b3-26ca-4bdb-9226-d67560864f29
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 62b2f787f2ba70c847d51cbee5b46c26719b9fc2
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="schema-rowset-classes-and-typedef-classes"></a>Şema Satır Kümesi Sınıfları ve Typedef Sınıfları
Bir şema, sahip olduğu veya belirli bir kullanıcı tarafından oluşturulan veritabanı nesneleri koleksiyonudur. Bir katalog bir veya daha fazla şemaları içerebilir, ancak her zaman görünümler ve etki alanı bilgileri şemasının içeren INFORMATION_SCHEMA adlı bir şema içermelidir. OLE DB'de şema bilgileri önceden tanımlanmış şema satır kümeleri kullanılarak alınır ve türleri, tablolar, sütunlar, dizinler, görünümler, onaylar ve kısıtlamaları, istatistikleri, karakter kümesi, harmanlamaları ve etki alanlarını içerir.  
  
 Şema satır kümeleri meta verisini temsil eden önceden tanımlanmış satır kümeleri ' dir. Şema satır kümeleri, burada veritabanı yapısı derleme zamanında bilinmiyor dinamik programlamada genellikle kullanılır. Çalışma zamanında bir veritabanı hakkında bilgi edinmek için bu şema satır kümeleri kullanabilirsiniz.  
  
 Typedef sınıfları şema satır kümeleri oluşturmak için kullanın. Şema satır kümesi sınıfları ve karşılık gelen typedef aşağıda listelenmiştir. Çağırmalısınız [CRestrictions::Open](../../data/oledb/crestrictions-open.md) şema satır kümesi örneği oluşturduktan sonra. Bu yöntem belirttiğiniz kısıtlamalara göre bir sonuç kümesi döndürür. Bkz: [IDBSchemaRowset](https://msdn.microsoft.com/en-us/library/ms713686.aspx) her şeması satır kümesi ile ilişkili kısıtlama sütunlar hakkında bilgi için.  
  
 Aşağıdaki tabloda her OLE DB şeması satır kümesi ve ilgili görüntüler OLE DB Şablonları typedef sınıfı ve bilgi sınıfı.  
  
|OLE DB şeması satır kümesi|TypeDef sınıfı|Bilgi sınıfı|  
|--------------------------|-------------------|----------------|  
|[ONAYLAR](https://msdn.microsoft.com/en-us/library/ms719776.aspx)|[CAssertions](../../data/oledb/cassertions-cassertioninfo.md)|[Cassertionınfo](../../data/oledb/cassertions-cassertioninfo.md)|  
|[KATALOG](https://msdn.microsoft.com/en-us/library/ms721241.aspx)|[CCatalogs](../../data/oledb/ccatalogs-ccataloginfo.md)|[Ccatalogınfo](../../data/oledb/ccatalogs-ccataloginfo.md)|  
|[CHARACTER_SETS](https://msdn.microsoft.com/en-us/library/ms722638.aspx)|[CCharacterSets](../../data/oledb/ccharactersets-ccharactersetinfo.md)|[CCharacterSetInfo](../../data/oledb/ccharactersets-ccharactersetinfo.md)|  
|[HARMANLAMALAR](https://msdn.microsoft.com/en-us/library/ms715783.aspx)|[CCollations](../../data/oledb/ccollations-ccollationinfo.md)|[Ccollationınfo](../../data/oledb/ccollations-ccollationinfo.md)|  
|[COLUMN_PRIVILEGES](https://msdn.microsoft.com/en-us/library/ms715800.aspx)|[CColumnPrivileges](../../data/oledb/ccolumnprivileges-ccolumnprivilegeinfo.md)|[Ccolumnprivilegeınfo](../../data/oledb/ccolumnprivileges-ccolumnprivilegeinfo.md)|  
|[SÜTUNLARI](https://msdn.microsoft.com/en-us/library/ms723052.aspx)|[CColumns](../../data/oledb/ccolumns-ccolumnsinfo.md)|[Ccolumnsınfo](../../data/oledb/ccolumns-ccolumnsinfo.md)|  
|[CONSTRAINT_COLUMN_USAGE](https://msdn.microsoft.com/en-us/library/ms724522.aspx)|[CConstraintColumnUsage](../../data/oledb/cconstraintcolumnusage-cconstraintcolumnusageinfo.md)|[CConstraintColumnUsageInfo](../../data/oledb/cconstraintcolumnusage-cconstraintcolumnusageinfo.md)|  
|[CONSTRAINT_TABLE_USAGE](https://msdn.microsoft.com/en-us/library/ms713710.aspx)|[CConstraintTableUsage](../../data/oledb/cconstrainttableusage-cconstrainttableusageinfo.md)|[Cconstrainttableusageınfo](../../data/oledb/cconstrainttableusage-cconstrainttableusageinfo.md)|  
|[CHECK_CONSTRAINTS](https://msdn.microsoft.com/en-us/library/ms712845.aspx)|[CCheckConstraints](../../data/oledb/ccheckconstraints-ccheckconstraintinfo.md)|[Ccheckconstraintınfo](../../data/oledb/ccheckconstraints-ccheckconstraintinfo.md)|  
|[COLUMN_DOMAIN_USAGE](https://msdn.microsoft.com/en-us/library/ms711240.aspx)|[CColumnDomainUsage](../../data/oledb/ccolumndomainusage-ccolumndomainusageinfo.md)|[Ccolumndomainusageınfo](../../data/oledb/ccolumndomainusage-ccolumndomainusageinfo.md)|  
|[FOREIGN_KEYS](https://msdn.microsoft.com/en-us/library/ms711276.aspx)|[CForeignKeys](../../data/oledb/cforeignkeys-cforeignkeysinfo.md)|[CForeignKeysInfo](../../data/oledb/cforeignkeys-cforeignkeysinfo.md)|  
|[DİZİNLER](https://msdn.microsoft.com/en-us/library/ms709712.aspx)|[Cındexes](../../data/oledb/cindexes-cindexinfo.md)|[Cındexınfo](../../data/oledb/cindexes-cindexinfo.md)|  
|[KEY_COLUMN_USAGE](https://msdn.microsoft.com/en-us/library/ms712990.aspx)|[CKeyColumnUsage](../../data/oledb/ckeycolumns-ckeycolumninfo.md)|[CKeyColumnUsageInfo](../../data/oledb/ckeycolumns-ckeycolumninfo.md)|  
|[PRIMARY_KEYS](https://msdn.microsoft.com/en-us/library/ms714362.aspx)|[CPrimaryKeys](../../data/oledb/cprimarykeys-cprimarykeyinfo.md)|[Cprimarykeyınfo](../../data/oledb/cprimarykeys-cprimarykeyinfo.md)|  
|[YORDAMLARI](https://msdn.microsoft.com/en-us/library/ms724021.aspx)|[CProcedures](../../data/oledb/cprocedures-cprocedureinfo.md)|[Cprocedureınfo](../../data/oledb/cprocedures-cprocedureinfo.md)|  
|[PROCEDURE_COLUMNS](https://msdn.microsoft.com/en-us/library/ms723092.aspx)|[CProcedureColumns](../../data/oledb/cprocedurecolumns-cprocedurecolumninfo.md)|[Cprocedurecolumnınfo](../../data/oledb/cprocedurecolumns-cprocedurecolumninfo.md)|  
|[PROCEDURE_PARAMETERS](https://msdn.microsoft.com/en-us/library/ms713623.aspx)|[CProcedureParameters](../../data/oledb/cprocedureparameters-cprocedureparaminfo.md)|[CProcedureParameterInfo](../../data/oledb/cprocedureparameters-cprocedureparaminfo.md)|  
|[PROVIDER_TYPES](https://msdn.microsoft.com/en-us/library/ms709785.aspx)|[CProviderTypes](../../data/oledb/cprovidertypes-cproviderinfo.md)|[Cproviderınfo](../../data/oledb/cprovidertypes-cproviderinfo.md)|  
|[REFERENTIAL_CONSTRAINTS](https://msdn.microsoft.com/en-us/library/ms719737.aspx)|[CReferentialConstraints](../../data/oledb/creferentialconstraints-creferentialconstraintinfo.md)|[CReferentialConstraintInfo](../../data/oledb/creferentialconstraints-creferentialconstraintinfo.md)|  
|[ŞEMALARIN](https://msdn.microsoft.com/en-us/library/ms716887.aspx)|[CSchemata](../../data/oledb/cschemata-cschematainfo.md)|[Cschemataınfo](../../data/oledb/cschemata-cschematainfo.md)|  
|[SQL_LANGUAGES](https://msdn.microsoft.com/en-us/library/ms714374.aspx)|[CSQLLanguages](../../data/oledb/csqllanguages-csqllanguageinfo.md)|[Csqllanguageınfo](../../data/oledb/csqllanguages-csqllanguageinfo.md)|  
|[İSTATİSTİKLERİ](https://msdn.microsoft.com/en-us/library/ms715957.aspx)|[CStatistics](../../data/oledb/cstatistics-cstatisticinfo.md)|[Cstatisticınfo](../../data/oledb/cstatistics-cstatisticinfo.md)|  
|[TABLE_CONSTRAINTS](https://msdn.microsoft.com/en-us/library/ms715921.aspx)|[CTableConstraints](../../data/oledb/ctableconstraints-ctableconstraintinfo.md)|[Ctableconstraintınfo](../../data/oledb/ctableconstraints-ctableconstraintinfo.md)|  
|[TABLOLARI](https://msdn.microsoft.com/en-us/library/ms716980.aspx)|[CTables](../../data/oledb/ctables-ctableinfo.md)|[Ctableınfo](../../data/oledb/ctables-ctableinfo.md)|  
|[TABLE_PRIVILEGES](https://msdn.microsoft.com/en-us/library/ms725428.aspx)|[CTablePrivileges](../../data/oledb/ctableprivileges-ctableprivilegeinfo.md)|[Ctableprivilegeınfo](../../data/oledb/ctableprivileges-ctableprivilegeinfo.md)|  
|[ÇEVİRİLER](https://msdn.microsoft.com/en-us/library/ms725365.aspx)|[CTranslations](../../data/oledb/ctranslations-ctranslationinfo.md)|[CTranslationInfo](../../data/oledb/ctranslations-ctranslationinfo.md)|  
|[USAGE_PRIVILEGES](https://msdn.microsoft.com/en-us/library/ms722743.aspx)|[CUsagePrivileges](../../data/oledb/cusageprivileges-cusageprivilegeinfo.md)|[Cusageprivilegeınfo](../../data/oledb/cusageprivileges-cusageprivilegeinfo.md)|  
|[VIEW_COLUMN_USAGE](https://msdn.microsoft.com/en-us/library/ms714896.aspx)|[CViewColumnUsage](../../data/oledb/cviewcolumnusage-cviewcolumninfo.md)|[CViewColumnInfo](../../data/oledb/cviewcolumnusage-cviewcolumninfo.md)|  
|[GÖRÜNÜMLER](https://msdn.microsoft.com/en-us/library/ms723122.aspx)|[CViews](../../data/oledb/cviews-cviewinfo.md)|[Cviewınfo](../../data/oledb/cviews-cviewinfo.md)|  
|[VIEW_TABLE_USAGE](https://msdn.microsoft.com/en-us/library/ms719727.aspx)|[CViewTableUsage](../../data/oledb/cviewtableusage-cviewtableinfo.md)|[Cviewtableınfo](../../data/oledb/cviewtableusage-cviewtableinfo.md)|  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldbsch.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CRestrictions Sınıfı](../../data/oledb/crestrictions-class.md)