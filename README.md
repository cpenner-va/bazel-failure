# Reproducability steps:

Run

```sh
bazel build //:failure_case
```


Which fails with:
```
Unhandled exception thrown during build; message: Unrecoverable error while evaluating node 'CONFIGURED_TARGET://:failure_case 5884f1ddd33770b55053bc68c040314c (1178570733 112078612)' (requested by nodes )
INFO: Elapsed time: 0.874s
java.lang.RuntimeException: Unrecoverable error while evaluating node 'CONFIGURED_TARGET://:failure_case 5884f1ddd33770b55053bc68c040314c (1178570733 112078612)' (requested by nodes )
        at com.google.devtools.build.skyframe.ParallelEvaluator$Evaluate.run(ParallelEvaluator.java:472)
        at com.google.devtools.build.lib.concurrent.AbstractQueueVisitor$WrappedRunnable.run(AbstractQueueVisitor.java:497)
        at java.util.concurrent.ThreadPoolExecutor.runWorker(ThreadPoolExecutor.java:1142)
        at java.util.concurrent.ThreadPoolExecutor$Worker.run(ThreadPoolExecutor.java:617)
        at java.lang.Thread.run(Thread.java:745)
Caused by: java.lang.IllegalArgumentException: No such attribute testonly in maven_jar rule //external:com_google_instrumentation_instrumentation_api
        at com.google.devtools.build.lib.packages.AbstractAttributeMapper.getIndexWithTypeCheck(AbstractAttributeMapper.java:229)
        at com.google.devtools.build.lib.packages.AbstractAttributeMapper.get(AbstractAttributeMapper.java:57)
        at com.google.devtools.build.lib.packages.NonconfigurableAttributeMapper.get(NonconfigurableAttributeMapper.java:45)
        at com.google.devtools.build.lib.bazel.rules.BazelRuleClassProvider$BazelPrerequisiteValidator.isTestOnlyRule(BazelRuleClassProvider.java:276)
        at com.google.devtools.build.lib.bazel.rules.BazelRuleClassProvider$BazelPrerequisiteValidator.validateDirectPrerequisiteForTestOnly(BazelRuleClassProvider.java:259)
        at com.google.devtools.build.lib.bazel.rules.BazelRuleClassProvider$BazelPrerequisiteValidator.validate(BazelRuleClassProvider.java:197)
        at com.google.devtools.build.lib.analysis.RuleContext$Builder.validateDirectPrerequisite(RuleContext.java:2011)
        at com.google.devtools.build.lib.analysis.RuleContext$Builder.createTargetMap(RuleContext.java:1679)
        at com.google.devtools.build.lib.analysis.RuleContext$Builder.build(RuleContext.java:1518)
        at com.google.devtools.build.lib.analysis.ConfiguredTargetFactory.createRule(ConfiguredTargetFactory.java:247)
        at com.google.devtools.build.lib.analysis.ConfiguredTargetFactory.createConfiguredTarget(ConfiguredTargetFactory.java:178)
        at com.google.devtools.build.lib.skyframe.SkyframeBuildView.createConfiguredTarget(SkyframeBuildView.java:489)
        at com.google.devtools.build.lib.skyframe.ConfiguredTargetFunction.createConfiguredTarget(ConfiguredTargetFunction.java:1128)
        at com.google.devtools.build.lib.skyframe.ConfiguredTargetFunction.compute(ConfiguredTargetFunction.java:261)
        at com.google.devtools.build.skyframe.ParallelEvaluator$Evaluate.run(ParallelEvaluator.java:398)
        ... 4 more
java.lang.RuntimeException: Unrecoverable error while evaluating node 'CONFIGURED_TARGET://:failure_case 5884f1ddd33770b55053bc68c040314c (1178570733 112078612)' (requested by nodes )
        at com.google.devtools.build.skyframe.ParallelEvaluator$Evaluate.run(ParallelEvaluator.java:472)
        at com.google.devtools.build.lib.concurrent.AbstractQueueVisitor$WrappedRunnable.run(AbstractQueueVisitor.java:497)
        at java.util.concurrent.ThreadPoolExecutor.runWorker(ThreadPoolExecutor.java:1142)
        at java.util.concurrent.ThreadPoolExecutor$Worker.run(ThreadPoolExecutor.java:617)
        at java.lang.Thread.run(Thread.java:745)
Caused by: java.lang.IllegalArgumentException: No such attribute testonly in maven_jar rule //external:com_google_instrumentation_instrumentation_api
        at com.google.devtools.build.lib.packages.AbstractAttributeMapper.getIndexWithTypeCheck(AbstractAttributeMapper.java:229)
        at com.google.devtools.build.lib.packages.AbstractAttributeMapper.get(AbstractAttributeMapper.java:57)
        at com.google.devtools.build.lib.packages.NonconfigurableAttributeMapper.get(NonconfigurableAttributeMapper.java:45)
        at com.google.devtools.build.lib.bazel.rules.BazelRuleClassProvider$BazelPrerequisiteValidator.isTestOnlyRule(BazelRuleClassProvider.java:276)
        at com.google.devtools.build.lib.bazel.rules.BazelRuleClassProvider$BazelPrerequisiteValidator.validateDirectPrerequisiteForTestOnly(BazelRuleClassProvider.java:259)
        at com.google.devtools.build.lib.bazel.rules.BazelRuleClassProvider$BazelPrerequisiteValidator.validate(BazelRuleClassProvider.java:197)
        at com.google.devtools.build.lib.analysis.RuleContext$Builder.validateDirectPrerequisite(RuleContext.java:2011)
        at com.google.devtools.build.lib.analysis.RuleContext$Builder.createTargetMap(RuleContext.java:1679)
        at com.google.devtools.build.lib.analysis.RuleContext$Builder.build(RuleContext.java:1518)
        at com.google.devtools.build.lib.analysis.ConfiguredTargetFactory.createRule(ConfiguredTargetFactory.java:247)
        at com.google.devtools.build.lib.analysis.ConfiguredTargetFactory.createConfiguredTarget(ConfiguredTargetFactory.java:178)
        at com.google.devtools.build.lib.skyframe.SkyframeBuildView.createConfiguredTarget(SkyframeBuildView.java:489)
        at com.google.devtools.build.lib.skyframe.ConfiguredTargetFunction.createConfiguredTarget(ConfiguredTargetFunction.java:1128)
        at com.google.devtools.build.lib.skyframe.ConfiguredTargetFunction.compute(ConfiguredTargetFunction.java:261)
        at com.google.devtools.build.skyframe.ParallelEvaluator$Evaluate.run(ParallelEvaluator.java:398)
        ... 4 more
```
