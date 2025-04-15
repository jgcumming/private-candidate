all: pyang yanglint

pyang:
	pyang --ietf --strict \
	    -p yang \
	    -f tree \
	    yang/ietf-netconf-private-candidate@2024-09-12.yang \
	    -o ietf-netconf-private-candidate.pyang-tree

yanglint:
	yanglint \
	    -p yang \
	    -f tree \
	    yang/ietf-netconf-private-candidate@2024-09-12.yang \
	    -o ietf-netconf-private-candidate.yanglint-tree

tests: test1

test1:
	@yanglint \
	   -p yang \
	   -F ietf-netconf-private-candidate:private-candidate \
	   -t nc-rpc \
	   yang/ietf-netconf@2011-06-01.yang \
	   yang/ietf-netconf-private-candidate@2024-09-12.yang \
	   data/data1.xml \

clean:
	rm *-tree

