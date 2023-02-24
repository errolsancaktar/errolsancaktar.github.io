# Options
RESUME_NAME ?= resume
LANGUAGE ?= en
BUILD_DIR ?= out

# Internal variables
RESUME_TARGET ?= $(BUILD_DIR)/$(LANGUAGE)/$(RESUME_NAME).pdf

display_info = @echo -e "[\E[32;01m*\E[0m]$(1)"

all: $(RESUME_TARGET)

$(RESUME_TARGET): resume_config.yaml
	mkdir -p $(dir $@)
	$(call display_info, "Create $@ from $< with language $(LANGUAGE)")
	pwd
	ls -lah
	ls -lah ../
	ls -lah ../../
	ls -lah ../resumy
	python3 -m pip install --upgrade ../resumy/dist/*.whl
	python3 ../resumy/src/resumy/resumy.py build $< -o $@
	$(call display_info, "Successfully created $@")

clean:
	@rm -rf out
