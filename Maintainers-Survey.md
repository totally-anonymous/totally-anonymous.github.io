# Maintainers Survey

Dear XXX,

as a kernel maintainer, you know the role of the MAINTAINERS file, and related tooling. We are interested if the steps of patch integration
(V1->V2->…->Vn->repo) happen in alignment with MAINTAINERS. This is especially of importance when Linux is being used in environments that require strict adherence to development processes, for instance safety-critical systems like automobiles or medical devices.

As our early-stage analysis shows, 'regular' or 'correct' integration of patches increased from ~65% in 2011 to ~90% in 2022. This allows for drawing conclusions on the scaleability of the project, and the significance and growing importance of well-organised processes.

There are always some corner cases where automatic evaluation shows "violations" of irregular integration, while there are justifiable reasons. Hence, we are working on clustering closely related entries in MAINTAINERS (e.g., NETWORKING [GENERAL], NETWORKING DRIVERS, ARM PORT, ...) by analysing code overlaps between entries. This gives us the opportunity to derive a first formal model of what "subsystems" in Linux could be.

As you're an expert in this domain, we would like to learn your opinion on some edge cases that we observed, in order to strengthen the plausibility of our results.

We would appreciate if you find some minutes to tell us your opinion on the integration process of the following two commits.


# 5dc33592e95 ("lockdep: Allow tuning tracing capacity constants.")

Tetsuo Handa authored and committed 5dc33592e95 in Apr'21, a patch that affects the LOCKING PRIMITIVES entry in MAINTAINERS. The last revision (V5) of this patch was being sent to lists in Feb'21 [1]. At that point in time, the latest release was v5.11.

Running v5.11:./scripts/get_maintainers.pl against this commit will not show Tetsuo as a valid maintainer for LOCKING PRIMITIVES. However, Tetsuo is a maintainer, but for the unrelated TOMOYO SECURITY MODULE entry.

What are your thoughts on this situation? In your opinion, is it reasonable that Tetsuo routed the patch via his tree?


# 4499d488f6e ("drm/edid: Parse MAX_FRL field from HFVSDB block")

Swati Sharma authored 4499d488f6e, and was committed by Jani Nikula in Dec'20. The last revision (V5) of this patch can be found here [2]. This patch affects DRM DRIVERS AND MISC GPU PATCHES and DRM DRIVERS. At the time of writing the patch, the latest kernel release was v5.10.

Running v5.10:./scripts/get_maintainers.pl against this commit will not show Jani as a valid maintainer for any of those entries. However, Jani is in charge of INTEL DRM DRIVERS.

What are your thoughts on this situation?

Thanks,
  XXX

[1] https://lore.kernel.org/all/20210208102551.5256-1-penguin-kernel@I-love.SAKURA.ne.jp/

[2] https://lore.kernel.org/all/20201216053121.18819-3-ankit.k.nautiyal@intel.com/
