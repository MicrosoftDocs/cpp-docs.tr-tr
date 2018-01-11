---
title: "C++ sınıflarında dllimport ve dllexport kullanma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
helpviewer_keywords:
- exporting classes [C++]
- declarations [C++], class
- exportable classes [C++]
- classes [C++], declaring
- classes [C++], exportable and inheritance
- inheritance [C++], exportable classes [C++]
- dllimport attribute [C++], classes
- declaring classes [C++]
- dllexport attribute [C++]
- dllexport attribute [C++], classes [C++]
ms.assetid: 8d7d1303-b9e9-47ca-96cc-67bf444a08a9
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: d8f9434387efcf3377cdc983116a51b524d16662
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="using-dllimport-and-dllexport-in-c-classes"></a>C++ Sınıflarında dllimport ve dllexport Kullanma
## <a name="microsoft-specific"></a>Microsoft'a Özgü  
 C++ sınıfları ile bildirebilir **dllimport** veya `dllexport` özniteliği. Bu formlar bütün sınıfı içe veya dışa kapsıyor. Bu şekilde dışarı sınıfları dışarı aktarılabilir sınıflar olarak adlandırılır.  
  
 Aşağıdaki örnek, dışarı aktarılabilir bir sınıfı tanımlar. Tüm üye işlevleri ve statik verileri dışarı aktarılır:  
  
```  
#define DllExport   __declspec( dllexport )  
  
class DllExport C {  
   int i;  
   virtual int func( void ) { return 1; }  
};  
```  
  
 Bu açık kullanımına dikkat edin **dllimport** ve `dllexport` dışarı aktarılabilir bir sınıf üyeleri özniteliklerinde yasaktır.  
  
##  <a name="_pluslang_using_dllimport_and_dllexport_in_c2b2bdllexportclasses"></a>dllexport sınıfları  
 Bir sınıf bildirme zaman `dllexport`, tüm üye işlevleri ve statik veri üyeleri dışarı aktarılır. Bu tür üyeleri aynı program tanımlarını sağlamanız gerekir. Aksi halde, bir bağlayıcı hatası oluşturulur. Bu kural için bir özel olduğu için açık tanımları sağlamak zorunda değildir saf sanal işlevler için geçerlidir. Ancak, saf sanal Yıkıcılar her zaman bir yıkıcı bir Özet sınıf için temel sınıf yıkıcı tarafından her zaman çağrıldığı için bir tanım sağlamanız gerekir. Bu kurallar nonexportable sınıfları için aynı olduğunu unutmayın.  
  
 Sınıf türü ya da sınıfları döndüren işlevler veri veriyorsanız, dışa aktarma sınıfı emin olun.  
  
##  <a name="_pluslang_dllexport_classesdllexportclasses"></a>dllimport sınıfları  
 Bir sınıf bildirme zaman **dllimport**, tüm üye işlevleri ve statik veri üyeleri alınır. Davranışını aksine **dllimport** ve `dllexport` nonclass türlerinde, aynı programda, bir tanım statik veri üyeleri belirtemezsiniz bir **dllimport** sınıfı tanımlanır.  
  
##  <a name="_pluslang_using_dllimport_and_dllexport_in_c2b2binheritanceandexportableclasses"></a>Devralma ve dışarı aktarılabilir sınıflar  
 Dışarı aktarılabilir bir sınıfın tüm temel sınıfları dışarı aktarılabilir olması gerekir. Aksi durumda, derleyici uyarısı oluşturulur. Ayrıca, aynı zamanda sınıflarıdır tüm erişilebilir üyeleri dışarı aktarılabilir olması gerekir. Bu kural izin veriyorsa bir `dllexport` devralınacak sınıfı bir **dllimport** sınıfı ve bir **dllimport** devralınacak sınıfı bir `dllexport` (ikinci Önerilmemesine rağmen) sınıfı. Bir kural olarak, DLL istemci (göre C++ erişim kuralları) için erişilebilir olan her şeyi verilebilir arabirimi parçası olması gerekir. Satır içi işlevlerde başvurulan özel veri üyelerini içerir.  
  
##  <a name="_pluslang_using_dllimport_and_dllexport_in_c2b2bselectivememberimportexport"></a>Seçmeli üye içeri/dışarı aktarma  
 Üye işlevleri ve bir sınıftaki statik verileri dış bağlantı örtük olarak olduğu için bildirebilir **dllimport** veya `dllexport` bütün sınıfı dışarı sürece özniteliği. Tüm sınıf içe veya dışa, üye işlevleri ve veri olarak açık bildirimi **dllimport** veya `dllexport` engellendi. Statik veri üyesi bir sınıf tanımı içinde bildirme varsa `dllexport`, bir tanım herhangi bir yerde (ile nonclass dış bağlantı gibi) aynı programın içinde gerçekleşmelidir.  
  
 Benzer şekilde, üye işlevleri ile bildirebilir **dllimport** veya `dllexport` öznitelikleri. Bu durumda, sağlamanız gereken bir `dllexport` aynı program içinde tanımı.  
  
 Birkaç önemli nokta seçmeli üye içeri ve dışarı aktarma ile ilgili dikkat edilecek faydalı olur:  
  
-   Seçmeli üye içeri/dışarı aktarma en iyi şekilde daha kısıtlayıcı dışarı aktarılan sınıf arabirimi sürümünü sağlamak için kullanılır; diğer bir deyişle, bir dilden daha az ortak ve özel özellikleri kullanıma sunan bir DLL tasarlayabilirsiniz aksi olanak tanır. De dışarı aktarılabilir arabirimi ince ayar yapmak için kullanışlıdır: istemci tanımı tarafından bazı özel veri erişemiyor olduğunu bildiğiniz durumlarda, tüm sınıf vermeniz gerekmez.  
  
-   Bir sınıftaki bir sanal işlev veriyorsanız, bunların tümünü vermek veya en az istemci doğrudan kullanabileceğiniz sürümlerinin sağlamanız gerekir.  
  
-   Sanal işlevler ile seçmeli üye içeri/dışarı aktarma kullanmakta olduğunuz bir sınıf varsa, işlevleri verilebilir arabiriminde olmalıdır veya satır içi (istemciye görünür) tanımlı.  
  
-   Bir üye olarak tanımlarsanız `dllexport` ancak sınıf tanımında dahil etmeyin, derleyici hatası oluşturulur. Üye sınıfı üstbilgisinde tanımlamanız gerekir.  
  
-   Rağmen sınıf üyeleri tanımını **dllimport** veya `dllexport` olan izin verilen, sınıf tanımında belirtilen arabirimi geçersiz kılamaz.  
  
-   İçinde bildirilen bu sınıf tanımını gövdesi dışında bir yerde üye işlevi tanımlarsanız işlevi olarak tanımlanmış olması durumunda bir uyarı oluşturulduğu `dllexport` veya **dllimport** (Bu tanımı farklıysa sınıf bildiriminde belirtilen).  
  
**SON Microsoft özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [dllexport, dllimport](../cpp/dllexport-dllimport.md)