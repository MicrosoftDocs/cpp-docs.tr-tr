---
title: Kilitlenme Davranışını Yorumlama
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- _Releases_nonreentrant_lock_
- _Lock_kind_mutex_
- _Lock_kind_critical_section_
- _Acquires_lock_
- _Releases_lock_
- _Has_lock_kind_
- _Releases_exclusive_lock_
- _Post_same_lock_
- _Requires_exclusive_lock_held_
- _Requires_shared_lock_held_
- _Lock_kind_semaphore_
- _Requires_lock_held_
- _Acquires_exclusive_lock_
- _Create_lock_level_
- _Acquires_nonreentrant_lock_
- _Releases_shared_lock_
- _Has_lock_level_
- _Lock_kind_spin_lock_
- _Requires_lock_not_held_
- _Acquires_shared_lock_
- _Requires_no_locks_held_
- _Lock_level_order_
- _Lock_kind_event_
ms.assetid: 07769c25-9b97-4ab7-b175-d1c450308d7a
ms.openlocfilehash: 8966d982b7bcbe9844a7bf1ec3088c2a9424b23a
ms.sourcegitcommit: 7bea0420d0e476287641edeb33a9d5689a98cb98
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/17/2020
ms.locfileid: "77418643"
---
# <a name="annotating-locking-behavior"></a>Kilitlenme Davranışını Yorumlama

Çok iş parçacıklı programınızda eşzamanlılık hatalarından kaçınmak için, her zaman uygun bir tane disiplin ve SAL ek açıklamalarını kullanın.

Eşzamanlılık hataları, belirleyici olmayan bir şekilde yeniden oluşturmak, tanılamak ve hata ayıklamak için çok zor. İş parçacığı araya ekleme hakkında bilgi, en iyi şekilde zordur ve birkaç iş parçacığına sahip bir kod gövdesi tasarlarken pratik hale gelir. Bu nedenle, çok iş parçacıklı programlarınızda bir kilitleme disiplini izlemek iyi bir uygulamadır. Örneğin, birden çok kilit edinirken bir kilit sırasını uygulamaya getirmek, kilitlenmeleri önlemeye yardımcı olur ve paylaşılan bir kaynağa erişmeden önce doğru koruma kilitlenmesinin, yarış koşullarından kaçınmanıza yardımcı olur.

Ne yazık ki, ortaya çıkacak basit kilitleme kurallarının uygulamada izlenmesi çok zor olabilir. Bugünün programlama dillerinde ve derleyicilerinin temel sınırlaması, eşzamanlılık gereksinimlerinin belirtimini ve analizini doğrudan desteklemeleridir. Programcıların kilitleri nasıl kullandıkları hakkında bilgi almak için resmi olmayan kod açıklamalarına güvenmeleri gerekir.

Eşzamanlılık SAL ek açıklamaları, kilitleme yan etkileri, kilitleme sorumluluğu, veri koruyucuları, kilit sırası hiyerarşisi ve diğer beklenen kilitleme davranışını belirtmenize yardımcı olacak şekilde tasarlanmıştır. Örtülü kuralları açık hale getirerek SAL eşzamanlılık ek açıklamaları, kodunuzun kilitleme kurallarını nasıl kullandığını belgelemeniz için tutarlı bir yol sağlar. Eşzamanlılık ek açıklamaları Ayrıca, kod analizi araçlarının yarış koşullarını, kilitlenmeleri, eşleşmeyen eşitleme işlemlerini ve diğer hafif eşzamanlılık hatalarını bulma yeteneğini geliştirir.

## <a name="general-guidelines"></a>Genel Yönergeler

Ek açıklamaları kullanarak, uygulamalar (Callet 'ler) ve istemcileri (çağıranlar) arasında işlev tanımları tarafından kapsanan sözleşmeleri ve daha fazla analizi daha da iyileştirebilecek programın diğer özelliklerini belirtebilir.

SAL, birçok farklı kilit temel türünü destekler; Örneğin, kritik bölümler, zaman uyumu sağlayıcılar, döndürme kilitleri ve diğer kaynak nesneleri. Birçok eşzamanlılık ek açıklaması, bir kilit ifadesini parametre olarak alır. Kurala göre, bir kilit, temeldeki kilit nesnesinin yol ifadesiyle gösterilir.

Göz önünde bulundurmanız gereken bazı iş parçacığı sahiplik kuralları:

- Döndürme kilitleri, açık iş parçacığı sahipliğini içeren sayılmayan kilitlerdir.

- Birbirini kapsamalı ve kritik bölümler, açık iş parçacığı sahipliğini içeren kilitler olarak sayılır.

- Semaforlar ve olaylar, açık iş parçacığı sahipliğini olmayan kilitler olarak sayılır.

## <a name="locking-annotations"></a>Ek açıklamaları kilitleme

Aşağıdaki tabloda kilitleme ek açıklamaları listelenmektedir.

|Ek Açıklama|Açıklama|
|----------------|-----------------|
|`_Acquires_exclusive_lock_(expr)`|Bir işlevi inceleyin ve işlevin, `expr`tarafından adlandırılan kilit nesnesinin dışlamalı kilit sayısına göre artırdığını gösterir.|
|`_Acquires_lock_(expr)`|Bir işlevi daha fazla açıklama olarak gösterir ve bu işlevin, `expr`tarafından adlandırılan kilit nesnesinin kilit sayısıyla bir sonraki artışla geçtiğini belirtir.|
|`_Acquires_nonreentrant_lock_(expr)`|`expr` tarafından adlandırılan kilit elde edilir.  Kilit zaten tutuluyorsa bir hata bildirilir.|
|`_Acquires_shared_lock_(expr)`|Bir işlevi inceleyin ve işlevin, `expr`tarafından adlandırılan kilit nesnesinin paylaşılan kilit sayısıyla aynı şekilde geçtiğini gösterir.|
|`_Create_lock_level_(name)`|Ek açıklamaların `_Has_Lock_level_` ve `_Lock_level_order_`kullanılabilmesi için simgeyi `name` bir kilit düzeyi olarak bildiren bir ifade.|
|`_Has_lock_kind_(kind)`|Bir kaynak nesnesinin tür bilgilerini iyileştirmek için herhangi bir nesneye Açıklama Ekle. Bazen, farklı türlerde kaynaklar için ortak bir tür kullanılır ve aşırı yüklenmiş tür çeşitli kaynaklar arasındaki anlam gereksinimlerini ayırt etmek için yeterli değildir. Önceden tanımlanmış `kind` parametrelerinin listesi aşağıda verilmiştir:<br /><br /> `_Lock_kind_mutex_`<br /> Zaman uyumu sağlayıcılar için kilit türü KIMLIĞI.<br /><br /> `_Lock_kind_event_`<br /> Olaylar için kilit türü KIMLIĞI.<br /><br /> `_Lock_kind_semaphore_`<br /> Semaforlar için kilit türü KIMLIĞI.<br /><br /> `_Lock_kind_spin_lock_`<br /> Döndürme kilitleri için kilit türü KIMLIĞI.<br /><br /> `_Lock_kind_critical_section_`<br /> Kritik bölümler için kilit türü KIMLIĞI.|
|`_Has_lock_level_(name)`|Bir kilit nesnesine açıklama koyun ve `name`kilit düzeyini verir.|
|`_Lock_level_order_(name1, name2)`|`name1` ve `name2`arasında kilit sıralaması sağlayan bir ifade.  Düzeyi `name1` olan kilitler, düzeyi `name2`olmayan kilitlere göre alınmalıdır.|
|`_Post_same_lock_(expr1, expr2)`|Bir işlevi bir işleve açıklama olarak, `expr1` ve `expr2`olmak üzere iki kilit, aynı kilit nesnesi gibi değerlendirildiğini gösterir.|
|`_Releases_exclusive_lock_(expr)`|Bir işlevi bir işleve açıklama ve bu işlevin, `expr`tarafından adlandırılan kilit nesnesinin dışlamalı kilit sayısına göre ne kadar azaltır olduğunu gösterir.|
|`_Releases_lock_(expr)`|Bir işlevi daha fazla açıklama olarak gösterir ve işlevin, `expr`tarafından adlandırılan kilit nesnesinin kilit sayısına göre ne kadar azaltır.|
|`_Releases_nonreentrant_lock_(expr)`|`expr` tarafından adlandırılan kilit serbest bırakılır. Kilit Şu anda tutulmadığında bir hata bildirilir.|
|`_Releases_shared_lock_(expr)`|Bir işlevi daha fazla açıklama olarak gösterir ve işlevin, `expr`tarafından adlandırılan kilit nesnesinin paylaşılan kilit sayısına göre ne kadar azaltır.|
|`_Requires_lock_held_(expr)`|Bir işlevi inceleyin ve ön durum ' a `expr` tarafından adlandırılan nesnenin kilit sayısının en az bir tane olduğunu gösterir.|
|`_Requires_lock_not_held_(expr)`|Bir işlevi bir işleve açıklama ve ön durum ' a `expr` tarafından adlandırılan nesnenin kilit sayısının sıfır olduğunu gösterir.|
|`_Requires_no_locks_held_`|Bir işlevi inceleyin ve denetleyici tarafından bilinen tüm kilitlerin kilit sayısının sıfır olduğunu gösterir.|
|`_Requires_shared_lock_held_(expr)`|Bir işlevi inceleyin ve ön durumunda `expr` tarafından adlandırılan nesnenin paylaşılan kilit sayısının en az bir tane olduğunu gösterir.|
|`_Requires_exclusive_lock_held_(expr)`|Bir işlevi inceleyin ve ön durumunda `expr` tarafından adlandırılan nesnenin dışlamalı kilit sayısının en az bir tane olduğunu gösterir.|

## <a name="sal-intrinsics-for-unexposed-locking-objects"></a>Açığa çıkarmayan kilitleme nesneleri Için SAL Iç öğeler

Belirli kilit nesneleri ilişkili kilitleme işlevlerinin uygulanmasıyla gösterilmez.  Aşağıdaki tabloda, bu görünmeyen kilit nesnelerinde çalışan işlevlerde ek açıklamaları etkinleştiren açık iç değişkenler listelenmektedir.

|Ek Açıklama|Açıklama|
|----------------|-----------------|
|`_Global_cancel_spin_lock_`|İptal döndürme kilidini açıklar.|
|`_Global_critical_region_`|Kritik bölgeyi açıklar.|
|`_Global_interlock_`|Birbirine kenetlenmiş işlemleri açıklar.|
|`_Global_priority_region_`|Öncelik bölgesini açıklar.|

## <a name="shared-data-access-annotations"></a>Paylaşılan veri erişimi ek açıklamaları

Aşağıdaki tabloda, paylaşılan veri erişimi için ek açıklamalar listelenmektedir.

|Ek Açıklama|Açıklama|
|----------------|-----------------|
|`_Guarded_by_(expr)`|Bir değişkene açıklama koyun ve değişkene erişildiğinde, `expr` tarafından adlandırılan kilit nesnesinin kilit sayısının en az bir tane olduğunu gösterir.|
|`_Interlocked_`|Bir değişkene açıklama koyun ve `_Guarded_by_(_Global_interlock_)`eşdeğerdir.|
|`_Interlocked_operand_`|Açıklamalı işlev parametresi, çeşitli birbirine kilitli işlevlerden birinin hedef işlenendir.  Bu işlenenler özel ek özelliklere sahip olmalıdır.|
|`_Write_guarded_by_(expr)`|Bir değişken için bir açıklama ve değişken değiştirildiğinde, `expr` tarafından adlandırılan kilit nesnesinin kilit sayısı en az bir tane olur.|

## <a name="smart-lock-and-raii-annotations"></a>Akıllı Kilit ve OYıı ek açıklamaları

Akıllı kilitler genellikle yerel kilitleri sarın ve ömrünü yönetir. Aşağıdaki tabloda, `move` semantiği desteğiyle akıllı kilitler ve SEıı kodlama desenleriyle kullanılabilen ek açıklamalar listelenmektedir.

|Ek Açıklama|Açıklama|
|----------------|-----------------|
|`_Analysis_assume_smart_lock_acquired_`|Çözümleyiciye bir akıllı kilit elde edilen olduğunu varsaymasını söyler. Bu ek açıklama, parametresi olarak bir başvuru kilit türü bekliyor.|
|`_Analysis_assume_smart_lock_released_`|Çözümleyiciye, akıllı bir kilidin bırakıldığını varsaymasını söyler. Bu ek açıklama, parametresi olarak bir başvuru kilit türü bekliyor.|
|`_Moves_lock_(target, source)`|Kilit durumunu `source` nesnesinden `target`aktaran `move constructor` işlemini açıklar. `target` yeni oluşturulmuş bir nesne olarak kabul edilir, bu nedenle önce sahip olduğu tüm durumları kaybolur ve `source` durumuna göre değiştirilmez. `source` Ayrıca kilit sayısı veya diğer ad hedefi olmayan temiz bir duruma sıfırlanır, ancak ona işaret eden diğer adlar değişmeden kalır.|
|`_Replaces_lock_(target, source)`|Durumu kaynaktan aktarmadan önce hedef kilidinin serbest bırakıldığı `move assignment operator` semantiğini açıklar. Bu, önünde bir `_Releases_lock_(target)``_Moves_lock_(target, source)` birleşimi olarak kabul edilebilir.|
|`_Swaps_locks_(left, right)`|Nesneleri `left` ve `right` durumunu değiş tokuş eden standart `swap` davranışını tanımlar. Değiştirilen durum, varsa kilit sayısını ve diğer ad hedefini içerir. `left` ve `right` nesnelerine işaret eden diğer adlar değişmeden kalır.|
|`_Detaches_lock_(detached, lock)`|Bir kilit sarmalayıcı türünün içerdiği kaynakla ilişkilendirmesini geri almasına izin verdiği bir senaryoyu açıklar. Bu, `std::unique_ptr` iç işaretçiyle birlikte çalışmasına benzer: programcıların işaretçiyi ayıklamasına ve akıllı işaretçi kapsayıcısını temiz bir durumda bırakmasını sağlar. Benzer mantık `std::unique_lock` tarafından desteklenir ve özel kilit sarmalayıcılarını uygulanabilir. Ayrılmış kilit, kendi diğer adlarını korurken, bu nesnenin durumunu (varsa kilit sayısı ve diğer ad hedefi) korur. Kilit sayıları üzerinde hiçbir işlem yoktur (serbest bırakma ve alma). Bu ek açıklama, ayrılmış bağımsız değişkenin `this`değil `return` olması dışında tam olarak `_Moves_lock_` olarak davranır.|

## <a name="see-also"></a>Ayrıca bkz.

- [C/C++ Kod Hatalarını Azaltmak için SAL Ek Açıklamalarını Kullanma](../code-quality/using-sal-annotations-to-reduce-c-cpp-code-defects.md)
- [SAL'yi Anlama](../code-quality/understanding-sal.md)
- [İşlev Parametrelerini ve Dönüş Değerlerini Açıklama](../code-quality/annotating-function-parameters-and-return-values.md)
- [İşlev Davranışını Yorumlama](../code-quality/annotating-function-behavior.md)
- [Yapıları ve Sınıfları Yorumlama](../code-quality/annotating-structs-and-classes.md)
- [Açıklamanın Ne Zaman ve Nereye Uygulanacağını Belirtme](../code-quality/specifying-when-and-where-an-annotation-applies.md)
- [İç İşlevler](../code-quality/intrinsic-functions.md)
- [En İyi Yöntemler ve Örnekler](../code-quality/best-practices-and-examples-sal.md)
- [Kod Analizi ekip blogu](https://blogs.msdn.microsoft.com/codeanalysis/)
