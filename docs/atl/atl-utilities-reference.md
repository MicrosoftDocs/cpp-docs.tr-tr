---
title: "ATL yardımcı programları başvurusu | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
ms.assetid: dd8a2888-34f4-461e-9bf4-834218f9b95b
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 69f085df8b5dadbd0ba9d20596d37cb6313bb3f0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="atl-utilities-reference"></a>ATL Yardımcı Programları Başvurusu
ATL yolları ve URL'ler biçiminde işlemek için kod sağlar [CPathT](../atl/reference/cpatht-class.md) ve [CUrl](../atl/reference/curl-class.md). İş parçacığı havuzu [CThreadPool](../atl/reference/cthreadpool-class.md), uygulamalarınızda kullanılabilir. Bu kod, atlpath.h ve atlutil.h bulunabilir.  
  
### <a name="classes"></a>Sınıflar  
  
|||  
|-|-|  
|[CPathT Sınıfı](../atl/reference/cpatht-class.md)|Bu sınıf bir yolunu temsil eder.|  
|[CDebugReportHook Sınıfı](../atl/reference/cdebugreporthook-class.md)|Bu sınıf için bir adlandırılmış kanal hata ayıklama raporları göndermek için kullanın.|  
|[CNonStatelessWorker Sınıfı](../atl/reference/cnonstatelessworker-class.md)|Bir iş parçacığı havuzu isteklerini alır ve bunları oluşturulan ve yok bir alt nesne açın her istekte aktarır.|  
|[CNoWorkerThread Sınıfı](../atl/reference/cnoworkerthread-class.md)|Bu sınıf için bağımsız değişken olarak kullanma `MonitorClass` dinamik önbellek bakım devre dışı bırakmak istiyorsanız önbellek sınıflarına şablon parametresi.|  
|[CThreadPool Sınıfı](../atl/reference/cthreadpool-class.md)|Bu sınıf, iş öğelerinin sırasını işlemek çalışan iş parçacığı havuzu sağlar.|  
|[CUrl Sınıfı](../atl/reference/curl-class.md)|Bu sınıf, bir URL temsil eder. URL diğer bağımsız olarak her öğenin var olan bir URL Ayrıştırma olup olmadığını denetlemek tanır dize ya da sıfırdan bir dize oluşturma.|  
|[CWorkerThread Sınıfı](../atl/reference/cworkerthread-class.md)|Bu sınıf bir çalışan iş parçacığı oluşturur veya mevcut bir kullanır, bir veya daha fazla çekirdek nesne işleyicilerinin bekler ve tanıtıcıları birini işaret, belirtilen istemci işlevi yürütür.|  
  
### <a name="typedefs"></a>Tür tanımları  
  
|||  
|-|-|  
|[CPath](../atl/reference/atl-typedefs.md#cpath)|Bir alt uzmanlaşması [CPathT](../atl/reference/cpatht-class.md) kullanarak `CString`.|  
|[CPathA](../atl/reference/atl-typedefs.md#cpatha)|Bir alt uzmanlaşması [CPathT](../atl/reference/cpatht-class.md) kullanarak `CStringA`.|  
|[CPathW](../atl/reference/atl-typedefs.md#cpathw)|Bir alt uzmanlaşması [CPathT](../atl/reference/cpatht-class.md) kullanarak `CStringW`.|  
|[ATL_URL_PORT](../atl/reference/atl-typedefs.md#atl_url_port)|Tarafından kullanılan türü [CUrl](../atl/reference/curl-class.md) bir bağlantı noktası numarası belirtmek için.|  
  
### <a name="enums"></a>Numaralandırmalar  
  
|||  
|-|-|  
|[ATL_URL_SCHEME](../atl/reference/atl-url-scheme-enum.md)|Bu numaralandırma üyeleri tarafından anlaşılan düzenleri sabitleri sağlamak [CUrl](../atl/reference/curl-class.md).|  
  
### <a name="functions"></a>İşlevler  
  
|||  
|-|-|  
|[AtlCanonicalizeUrl](../atl/reference/atl-http-utility-functions.md#atlcanonicalizeurl)|Güvenli olmayan karakterleri ve boşlukları kaçış sıralarına dönüştürme içeren bir URL'yi kurallı hale getirmek için bu işlevi çağırın.|  
|[AtlCombineUrl](../atl/reference/atl-http-utility-functions.md#atlcombineurl)|Temel URL ile göreli bir URL'yi, kurallı tek bir URL'de birleştirmek için bu işlevi çağırın.|  
|[AtlEscapeUrl](../atl/reference/atl-http-utility-functions.md#atlescapeurl)|Tüm güvenli olmayan karakterleri kaçış sıralarına dönüştürmek için bu işlevi çağırın.|  
|[AtlGetDefaultUrlPort](../atl/reference/atl-http-utility-functions.md#atlgetdefaulturlport)|Belirli Internet Protokolü veya düzeni ile ilişkili varsayılan bağlantı noktası numarasını almak için bu işlevini çağırın.|  
|[AtlHexValue](../atl/reference/atl-text-encoding-functions.md#atlhexvalue)|Onaltılık basamağın sayısal değerini almak için bu işlevi çağırın.|  
|[AtlIsUnsafeUrlChar](../atl/reference/atl-http-utility-functions.md#atlisunsafeurlchar)|Bir karakterin URL'de kullanılmak üzere güvenli olup olmadığını öğrenmek için bu işlevi çağırın.|  
|[AtlUnescapeUrl](../atl/reference/atl-http-utility-functions.md#atlunescapeurl)|Kaçış karakterlerini orijinal değerlerine döndürmek için bu işlevi çağırın.|  
|[SystemTimeToHttpDate](../atl/reference/atl-http-utility-functions.md#systemtimetohttpdate)|Sistem saatini HTTP üstbilgileri kullanmak için uygun bir biçimde bir dizeye dönüştürmek için bu işlevi çağırın.|  

|[ATLPath::AddBackslash](../atl/reference/atl-path-functions.md#addbackslash)| Bu işlev için aşırı yüklenmiş bir sarmalayıcı olan [PathAddBackslash](http://msdn.microsoft.com/library/windows/desktop/bb773561). |  
|[ATLPath::AddExtension](../atl/reference/atl-path-functions.md#addextension)| Bu işlev için aşırı yüklenmiş bir sarmalayıcı olan [PathAddExtension](http://msdn.microsoft.com/library/windows/desktop/bb773563). |  
|[ATLPath::Append](../atl/reference/atl-path-functions.md#append)| Bu işlev için aşırı yüklenmiş bir sarmalayıcı olan [PathAppend](http://msdn.microsoft.com/library/windows/desktop/bb773565). |  
|[ATLPath::BuildRoot](../atl/reference/atl-path-functions.md#buildroot)| Bu işlev için aşırı yüklenmiş bir sarmalayıcı olan [PathBuildRoot](http://msdn.microsoft.com/library/windows/desktop/bb773567). |  
|[ATLPath::Canonicalize](../atl/reference/atl-path-functions.md#canonicalize)| Bu işlev için aşırı yüklenmiş bir sarmalayıcı olan [PathCanonicalize](http://msdn.microsoft.com/library/windows/desktop/bb773569). |  
|[ATLPath::Combine](../atl/reference/atl-path-functions.md#combine)| Bu işlev için aşırı yüklenmiş bir sarmalayıcı olan [PathCombine](http://msdn.microsoft.com/library/windows/desktop/bb773571). |  
|[ATLPath::CommonPrefix](../atl/reference/atl-path-functions.md#commonprefix)| Bu işlev için aşırı yüklenmiş bir sarmalayıcı olan [PathCommonPrefix](http://msdn.microsoft.com/library/windows/desktop/bb773574). |  
|[ATLPath::CompactPath](../atl/reference/atl-path-functions.md#compactpath)| Bu işlev için aşırı yüklenmiş bir sarmalayıcı olan [PathCompactPath](http://msdn.microsoft.com/library/windows/desktop/bb773575). |  
|[ATLPath::CompactPathEx](../atl/reference/atl-path-functions.md#compactpathex)| Bu işlev için aşırı yüklenmiş bir sarmalayıcı olan [PathCompactPathEx](http://msdn.microsoft.com/library/windows/desktop/bb773578). |  
|[ATLPath::FileExists](../atl/reference/atl-path-functions.md#fileexists)| Bu işlev için aşırı yüklenmiş bir sarmalayıcı olan [PathFileExists](http://msdn.microsoft.com/library/windows/desktop/bb773584). |  
|[ATLPath::FindExtension](../atl/reference/atl-path-functions.md#findextension)| Bu işlev için aşırı yüklenmiş bir sarmalayıcı olan [PathFindExtension](http://msdn.microsoft.com/library/windows/desktop/bb773587). |  
|[ATLPath::FindFileName](../atl/reference/atl-path-functions.md#findfilename)| Bu işlev için aşırı yüklenmiş bir sarmalayıcı olan [PathFindFileName](http://msdn.microsoft.com/library/windows/desktop/bb773589). |  
|[ATLPath::GetDriveNumber](../atl/reference/atl-path-functions.md#getdrivenumber)| Bu işlev için aşırı yüklenmiş bir sarmalayıcı olan [PathGetDriveNumber](http://msdn.microsoft.com/library/windows/desktop/bb773612). |  
|[ATLPath::IsDirectory](../atl/reference/atl-path-functions.md#isdirectory)| Bu işlev için aşırı yüklenmiş bir sarmalayıcı olan [PathIsDirectory](http://msdn.microsoft.com/library/windows/desktop/bb773621). |  
|[ATLPath::IsFileSpec](../atl/reference/atl-path-functions.md#isfilespec)| Bu işlev için aşırı yüklenmiş bir sarmalayıcı olan [PathIsFileSpec](http://msdn.microsoft.com/library/windows/desktop/bb773627). |  
|[ATLPath::IsPrefix](../atl/reference/atl-path-functions.md#isprefix)| Bu işlev için aşırı yüklenmiş bir sarmalayıcı olan [PathIsPrefix](http://msdn.microsoft.com/library/windows/desktop/bb773650). |  
|[ATLPath::IsRelative](../atl/reference/atl-path-functions.md#isrelative)| Bu işlev için aşırı yüklenmiş bir sarmalayıcı olan [PathIsRelative](http://msdn.microsoft.com/library/windows/desktop/bb773660). |  
|[ATLPath::IsRoot](../atl/reference/atl-path-functions.md#isroot)| Bu işlev için aşırı yüklenmiş bir sarmalayıcı olan [PathIsRoot](http://msdn.microsoft.com/library/windows/desktop/bb773674). |  
|[ATLPath::IsSameRoot](../atl/reference/atl-path-functions.md#issameroot)| Bu işlev için aşırı yüklenmiş bir sarmalayıcı olan [PathIsSameRoot](http://msdn.microsoft.com/library/windows/desktop/bb773687). |  
|[ATLPath::IsUNC](../atl/reference/atl-path-functions.md#isunc)| Bu işlev için aşırı yüklenmiş bir sarmalayıcı olan [PathIsUNC'yi](http://msdn.microsoft.com/library/windows/desktop/bb773712). |  
|[ATLPath::IsUNCServer](../atl/reference/atl-path-functions.md#isuncserver)| Bu işlev için aşırı yüklenmiş bir sarmalayıcı olan [PathIsUNCServer](http://msdn.microsoft.com/library/windows/desktop/bb773722). |  
|[ATLPath::IsUNCServerShare](../atl/reference/atl-path-functions.md#isuncservershare)| Bu işlev için aşırı yüklenmiş bir sarmalayıcı olan [PathIsUNCServerShare](http://msdn.microsoft.com/library/windows/desktop/bb773723). |  
|[ATLPath::MakePretty](../atl/reference/atl-path-functions.md#makepretty)| Bu işlev için aşırı yüklenmiş bir sarmalayıcı olan [PathMakePretty](http://msdn.microsoft.com/library/windows/desktop/bb773725). |  
|[ATLPath::MatchSpec](../atl/reference/atl-path-functions.md#matchspec)| Bu işlev için aşırı yüklenmiş bir sarmalayıcı olan [PathMatchSpec](http://msdn.microsoft.com/library/windows/desktop/bb773727). |  
|[ATLPath::QuoteSpaces](../atl/reference/atl-path-functions.md#quotespaces)| Bu işlev için aşırı yüklenmiş bir sarmalayıcı olan [PathQuoteSpaces](http://msdn.microsoft.com/library/windows/desktop/bb773739). |  
|[ATLPath::RelativePathTo](../atl/reference/atl-path-functions.md#relativepathto)| Bu işlev için aşırı yüklenmiş bir sarmalayıcı olan [PathRelativePathTo](http://msdn.microsoft.com/library/windows/desktop/bb773740). |  
|[ATLPath::RemoveArgs](../atl/reference/atl-path-functions.md#removeargs)| Bu işlev için aşırı yüklenmiş bir sarmalayıcı olan [PathRemoveArgs](http://msdn.microsoft.com/library/windows/desktop/bb773742). |  
|[ATLPath::RemoveBackslash](../atl/reference/atl-path-functions.md#removebackslash)| Bu işlev için aşırı yüklenmiş bir sarmalayıcı olan [PathRemoveBackslash](http://msdn.microsoft.com/library/windows/desktop/bb773743). |  
|[ATLPath::RemoveBlanks](../atl/reference/atl-path-functions.md#removeblanks)| Bu işlev için aşırı yüklenmiş bir sarmalayıcı olan [PathRemoveBlanks](http://msdn.microsoft.com/library/windows/desktop/bb773745). |  
|[ATLPath::RemoveExtension](../atl/reference/atl-path-functions.md#removeextension)| Bu işlev için aşırı yüklenmiş bir sarmalayıcı olan [PathRemoveExtension](http://msdn.microsoft.com/library/windows/desktop/bb773746). |  
|[ATLPath::RemoveFileSpec](../atl/reference/atl-path-functions.md#removefilespec)| Bu işlev için aşırı yüklenmiş bir sarmalayıcı olan [PathRemoveFileSpec](http://msdn.microsoft.com/library/windows/desktop/bb773748). |  
|[ATLPath::RenameExtension](../atl/reference/atl-path-functions.md#renameextension)| Bu işlev için aşırı yüklenmiş bir sarmalayıcı olan [PathRenameExtension](http://msdn.microsoft.com/library/windows/desktop/bb773749). |  
|[ATLPath::SkipRoot](../atl/reference/atl-path-functions.md#skiproot)| Bu işlev için aşırı yüklenmiş bir sarmalayıcı olan [PathSkipRoot](http://msdn.microsoft.com/library/windows/desktop/bb773754). |  
|[ATLPath::StripPath](../atl/reference/atl-path-functions.md#strippath)| Bu işlev için aşırı yüklenmiş bir sarmalayıcı olan [PathStripPath](http://msdn.microsoft.com/library/windows/desktop/bb773756). |  
|[ATLPath::StripToRoot](../atl/reference/atl-path-functions.md#striptoroot)| Bu işlev için aşırı yüklenmiş bir sarmalayıcı olan [PathStripToRoot](http://msdn.microsoft.com/library/windows/desktop/bb773757). |  
|[ATLPath::UnquoteSpaces](../atl/reference/atl-path-functions.md#unquotespaces)| Bu işlev için aşırı yüklenmiş bir sarmalayıcı olan [PathUnquoteSpaces](http://msdn.microsoft.com/library/windows/desktop/bb773763). |  
  

## <a name="see-also"></a>Ayrıca Bkz.  
 [Kavramları](../atl/active-template-library-atl-concepts.md)   
 [ATL COM Masaüstü Bileşenleri](../atl/atl-com-desktop-components.md)
